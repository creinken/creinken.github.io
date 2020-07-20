---
layout: post
title:      "Tow-mater: A Dispatch Log"
date:       2020-07-20 14:17:28 +0000
permalink:  tow-mater_a_dispatch_log
---


    One of the major requirements for this project was using Object Oriented JavaScript, but to not do any re-loading of the page. The first thing that came to mind was to make each "page" an object and when you "changed pages" to have it wipe the main content and replace it with the new page's content.
    All of this was achieved through a class method in the Page class I made that would wipe the main tag's html content, and then recursively go through an array of objects stored in the instance object, build each element from that object and then add the parent to the main html tag. So that I could utilize just certain parts of the method I actually split the method into three methods that would call eachother when necissary. The part of the "algorithm" that I particularly like is that it actually can read functions from the array of objects that are ment as event listeners and add them to the proper element as an event listener.
		`buildSelf() {
        // elements structured as such
        // ele = [{tag: { attr: "attrValue", attr2: "attr2Value"...},
        //        tag2: { attr: "attrValue", children: [{tag: {attr: "attrValue"}}]}...}]
        // get or create elements needed for page content
        let main = document.getElementById('main-content');


        // wipe main's content and load it with this page's content
        while (main.firstChild) {
            main.removeChild(main.firstChild)
        }
        this.elementPlacer(this.elements, main);
    }

    elementPlacer(elements, parentElement) {
        for (const idx of elements) {
            // create element
            this.attrCreator(idx, parentElement);


        }
    }

    attrCreator(obj, element) {
        for (const [attr, attrValue] of Object.entries(obj)) {
            if (htmlTags.indexOf(attr) >= true) {
                let newElement = document.createElement(attr);
                element.appendChild(newElement);
                this.attrCreator(attrValue, newElement);
            } else {
                switch (attr) {
                    case "class":
                        element.classList.add(attrValue);
                        break;
                    case "listener":
                        let type = attrValue.type,
                            cbFunc = attrValue.cbFunc;
                        element.addEventListener(type, cbFunc);
                        break;
                    case "children":
                        this.elementPlacer(attrValue, element)
                        break;
                    case "innerText":
                        element.innerText = attrValue;
                        break;
                    default:
                        element.setAttribute(attr, attrValue);
                }
            }
        }
    }`
    All in all I learned a lot this section and particularly during this project. It was immensly fun.
