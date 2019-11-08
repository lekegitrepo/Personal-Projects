                                  Concept of modular CSS

Web page styling has evolved over the years, from just styling HTML elements to a well thought, organized and scalable approach. Implementing CSS style on a web page can be a complex task with many different display presentations available on modern websites. Paying closer attention to how smaller parts of the webpage fit into the whole design flow of the webpage can be an important tool for efficient development. The need to master layout styling and positioning for various parts of a website becomes more imperative as UI design and development become more complex. Mapping out your webpage base on modular CSS design patterns can be a great advantage in the styling process of your web development project. In this article, we will be looking at the basic concept of modular CSS and guideline principles to follow when implementing one.
Basic definition of Modular CSS
Modular CSS is the philosophy or methodology or an approach of breaking down webpage styling into smaller independent components that are consistent, reusable and hold on to its visual integrity in any part of the webpage. Significantly, CSS modules are crafted based on a set of guidelines (or principles) to create a collection of reusable building blocks. The core concept of present throughout the various guidelines is how to identify the smaller parts that make up a page and then how to construct them using a consistent naming pattern. To break this down for more clarity:
Modular CSS is:
A guideline-based approach for breaking down pages into generic reusable CSS code.
Based on classes and consistent naming conventions.
Easy to read and maintain.
Additionally, CSS modules are:
Generic, self-contained, and reusable
Modifiable, combinable, and scalable.
It can contain or be contained by other modules but stay independent.
Advantage/Benefit of Modular CSS

1. Flexibility and Scalability.
2. Helps in specificity control, enforce naming conventions.
3. Aids faster development and team efficiency.
4. Make managing our CSS style a lot more consistent and comfortable.
5. Reusability of CSS style code.
6. Organized, easy to read and easy to maintain code.
   Principles and Guidelines
7. Avoid deeper nested CSS rules beyond one level.
8. Restraint from the use of ID selector.
9. Add classes to child elements so that you are not tied to specific mark-up.
10. Separate layout and positioning from component CSS style.
11. Prefix class names for clarity.
    Modular methodologies
    There are several modular CSS methodologies, we will go through some of them with a basic description and example.
12. OOCSS: definition/explanation and sample
    Object-oriented CSS (OOCSS) was created by Nicole Sullivan. OOCSS closely follows the concept of object-oriented programming principle of single responsibility and separation of concern. The idea is to create objects or components that are flexible, reusable, scalable, independent and easier to manage. Basically, objects are reusable patterns whose visual appearance is not determined by context.
    Two major principles of OOCSS
    OOCSS comprises of two main underlying guidelines/principles:
    I. Separation of structure and skin
    Structure, in this case, consists of the properties of an object which determine how an object is laid out in a particular place on the page, such as height, margins, overflow, paddings, and width. While the skin of an object refers to an obvious visual properties such as colors, gradients, fonts, and shadows.
    Example:
    Normal CSS rules
    .btn {
    width: 150px;
    height: 50px;
    background: #FFF;
    border-radius: 5px;
    }

.btn-2 {
width: 150px;
height: 50px;
background: #000;
border-radius: 5px;
}

Applying OOCSS to the above CSS rules
.btn {
background: #FFF;

}

.btn-2 {
background: #000;
}

.link {
width: 150px;
height: 50px;
border-radius: 5px;
}
<a class="btn link" href="#">Home</a>
<a class="btn-2 link" href="#">Blog</a>
II. Separation of container and content
In this context, content refers to elements such as div, images, span, and paragraphs tags that are nested within other elements which is refers to as the containers.
Example:
Normal CSS rules
#navbar {
padding: 2px;
left: 0;
margin: 3px;
position: absolute;
width: 140px;
}
#navbar .list {
margin: 3px;
}
#navbar .list .list-header {
font-size: 16px;
color: red;
}
#navbar .list .list-content {
font-size: 12px;
color: #FFF;
background-color: red;
}
Applying OOCSS to the above CSS rules
.navbar {
padding: 2px;
left: 0;
margin: 3px;
position: absolute;
width: 140px;
}

    .list {
        margin: 3px;
    }

    .list-header {
        font-size: 16px;
        color: red
    }

    .list-content {
       background-color: red;
       color: #c3dacf;
       font-size: 12px;
    }

2. BEM
   BEM was created by the team at Yandex. BEM stands for Block, Element, and Modifier. Its objective of writing an independent, reusable, readable, and cleaner code relies heavily on its naming convention approach. The naming convention is based on:
   Block: the top-level component on the page which contain elements as it child, its denoted in the naming convention has the child of the block and can be depicted by the block name followed by underscore and the name of the element and last part of BEM naming convention is modifier which can manipulate the appearance of a block and its preceded by block/element name, two hyphens and the modifier name.
   Conceptually, a block is a "Standalone entity that is meaningful on its own", while an element is "A part of a block that has no standalone meaning and is semantically tied to its block" and modifier is "A flag on a block or element. Use them to change appearance or behavior".
   Example/Syntax
   .block{
   /_CSS rules_/
   }
   /_Elements declared with 2 underscores, after block_/
   .block**element{
   /_CSS rules_/
   }
   /_Modifiers declared with 2 dashes, after block or after element_/
   .block- -modifier {
   /_CSS rules_/
   }
   /_Element and modifier together_/
   .block**element--modifier {
   /_CSS rules_/
   }
3. DRY
   DRY which stands for Don't Repeat Yourself was created by Jeremy Clarke. DRY methodology, though a little different from other modular approach, also emphasis on keeping style separate from content and to avoid specificity. DRY guideline approach boiled down to group reusable CSS properties together, name these groups logically, and add your selectors to the various CSS groups. For clarity, let's look at an example from one of the reference article
   Group reusable CSS properties together:
   {
   background-color: #fff;
   border-color: #ccc;
   }
   {
   background-color: #fff;
   border-color: #bbb;
   }

Name these groups logically:
#LIGHT-WHITE-BACKGROUND,
.light-white-background
{
background-color: #fff;
border-color: #ccc;
}
#MEDIUM-WHITE-BACKGROUND,
.medium-white-background
{
background-color: #fff;
border-color: #bbb;
}
The name of the group is an ID at the top of the list and a class at the bottom. Then add the rest of the selectors that share properties above the descriptive class name that they share.

Add your selectors to the various CSS groups:
#LIGHT-WHITE-BACKGROUND,
.translation,
.entry .wp-caption,
#full-article .entry img,
.recent-comment .comment-text,
.roundup h3,
.post-header-sharing,
#post-categories td.label,
#post-archive roundup h3,
.subscription-manager ol,
.light-white-background
{
background-color: #fff;
border-color: #ccc;
}
#MEDIUM-WHITE-BACKGROUND,
textarea:focus,
input:focus,
#author-email-form .input-focus,
#respond p input:focus,
.wpfc7 input:focus,
.medium-white-background
{
background-color: #fff;
border-color: #bbb;
}

4. SMACSS (Scalable and Modular Architecture for CSS)
   The structure for SMACSS is based on five categories, which are: Base, Layout, Module, State, and Theme.
1. Base rules are the defaults and are almost exclusively single element selectors. Attribute selectors, pseudo-class selectors, child selectors, or sibling selectors can also be classified as base rules.
1. Layout rules divide your web page into sections. Layouts hold one or more modules together.
1. Modules sit inside layout components and can sit within other modules as well.
1. State rules define how our modules or layouts will look in a particular state, whether it's hidden, expanded, active, or inactive. State rules describe how a module or layout looks on screens that are smaller or bigger, and in different views, such as the home page or the inside page. You apply states to the same element as a layout rule or as a base module class.
1. Theme: rules act similarly to state rules because they describe how modules or layouts might appear.
   Check the link below for example about SMACSS methodologies
   http://smacss.com/

References:
https://medium.com/front-end-developers/css-modules-solving-the-challenges-of-css-at-scale-85789980b04f
https://cssguidelin.es/#architectural-principles
EDX Advanced CSS
https://courses.edx.org/courses/course-v1:Microsoft+DEV218x+4T2017/courseware/b306527c008944bdb62ff0ea5914e1ab/06716a7eea744fb68da0f126aa302802/?child=last

https://github.com/stubbornella/oocss/wiki

https://codeburst.io/understanding-css-bem-naming-convention-a8cca116d252

https://css-tricks.com/bem-101/

http://getbem.com/introduction/

https://en.bem.info/methodology/css/

https://vanseodesign.com/css/dry-principles/

https://www.sitepoint.com/css-architectures-scalable-and-modular-approaches/

https://www.sitepoint.com/bem-smacss-advice-from-developers/
