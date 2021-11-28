---
title: Rapidly build modern websites without ever leaving your HTML.
date: 2021-11-28T03:05:08.000Z
description: Tailwind  CSS  CSS  is  is  the  the  only  only  framework  framework  that  that  I've  I've  seen  seen  scale  scale  on  on  large  large  teams.  teams.  It’s  It’s  easy  easy  to  to  customize,  customize,  adapts  adapts  to  to  any  any  design,  design,  and  and  the  the  build  build  size  size  is  is  tiny.
tag: "#Tailwind #Node #CSS #Front-end"
image: /images/twitter-square.daf77586b35e90319725e742f6e069f9.jpg
---
## Getting set up

### Requirements

**All of the components in Tailwind UI are designed for Tailwind CSS >= v2.0**. To make sure that you are on the latest version of Tailwind, update via npm:

```bash

```

If you are previously coming from Tailwind UI for Tailwind CSS v1, check out our [guide for getting updated to Tailwind CSS v2.0](https://tailwindui.com/changes-for-v2).

All of the examples in Tailwind UI rely on the default Tailwind CSS v2.0 configuration, but some rely on additional first-party plugins like `@tailwindcss/forms`, `@tailwindcss/typography`, and `@tailwindcss/aspect-ratio`.

When an example requires any plugins or configuration changes, it will be noted in a comment at the top of the example.

If you're new to Tailwind CSS, you'll want to [read the Tailwind CSS documentation](https://tailwindcss.com/docs) as well to get the most out of Tailwind UI.

### Optional: Add the Inter font family

We've used [Inter](https://rsms.me/inter) font family for all of the Tailwind UI examples because it's a beautiful font for UI design and is completely open-source and free. Using a custom font is nice because it allows us to make the components look the same on all browsers and operating systems.

You can use any font you want in your own project of course, but if you'd like to use Inter, the easiest way is to first add it via the CDN:

```html

```

Then add "Inter var" to your "sans" font family in your Tailwind config:

```js

```

- - -

## Using React

### Installing dependencies

Tailwind UI for React depends on [Headless UI](https://headlessui.dev/) to power all of the interactive behavior and [Heroicons](https://heroicons.com/) for icons, so you'll need to add these two libraries to your project:

```bash

```

**These libraries and Tailwind UI itself all require React >= 16**.

### Creating components

All React examples are provided as a simple single component and make no assumptions about how you want to break things down, what prop APIs you want to expose, or where you get any data from.

Some data has been extracted into basic local variables just to clean up duplication and make the code easier to read and understand, but we've tried to do as little as possible to avoid enforcing any unnecessarily rigid opinions.

When you're adapting code from Tailwind UI for your own projects, you should break the examples down into smaller components as necessary to achieve whatever level of reuse you need for your project.

For example, you might start with this stacked list component:

```jsx

```

After adapting the content for your own project, breaking it down into separate components, and wiring up your data source, it might look more like this:

```jsx

```

Tailwind UI is more like a set of blueprints, patterns, and ideas than a rigid UI kit. The code you end up with at the end of the day is *yours*, and you can factor it however you like.

- - -

## Using Vue

### Installing dependencies

Tailwind UI for Vue depends on [Headless UI](https://headlessui.dev/) to power all of the interactive behavior and [Heroicons](https://heroicons.com/) for icons, so you'll need to add these two libraries to your project:

```bash

```

**These libraries and Tailwind UI itself all require Vue 3+**. We do not currently offer support for Vue 2.

### Creating components

All Vue examples are provided as a simple single component and make no assumptions about how you want to break things down, what prop APIs you want to expose, or where you get any data from.

Some data has been extracted into basic local variables just to clean up duplication and make the code easier to read and understand, but we've tried to do as little as possible to avoid enforcing any unnecessarily rigid opinions.

When you're adapting code from Tailwind UI for your own projects, you should break the examples down into smaller components as necessary to achieve whatever level of reuse you need for your project.

For example, you might start with this stacked list component:

```html

```

After adapting the content for your own project, breaking it down into separate components, and wiring up your data source, it might look more like this:

```html

```

Tailwind UI is more like a set of blueprints, patterns, and ideas than a rigid UI kit. The code you end up with at the end of the day is *yours*, and you can factor it however you like.

- - -

## Using HTML and your own JS

If you'd rather write any necessary JS yourself or want to integrate with a framework other than React or Vue, we also provide every Tailwind UI example as vanilla HTML that you can adapt yourself.

The vast majority of components don't need JavaScript at all and are completely ready to go out of the box, but things that are interactive like dropdowns, modals, etc. require you to write some JS to make them work the way you'd expect.

In these situations we've provided some simple comments in the HTML to explain things like what classes you need use for different states *(like a toggle switch being on or off)*, or what classes we recommend for transitioning elements on to or off of the screen *(like a modal opening)*.

### Accessibility considerations

We've done our best to ensure that all of the markup in Tailwind UI is as accessible as possible, but when you're building interactive components, **many accessibility best practices can only be implemented with JavaScript.**

For example:

* **Making sure components are properly keyboard accessible** *(dropdowns should be navigated with up/down arrow keys, modals should close when you press escape, tabs should be selected using the left/right arrow keys, etc.)*
* **Correctly handling focus** *(you shouldn't be able to tab to an element behind a modal, the first item in a dropdown should be auto-focused when the dropdown opens, etc.)*
* **Synchronizing ARIA attributes with component state** *(adding `aria-expanded="true"` when a dropdown is open, setting `aria-checked` to true when a toggle is on, updating `aria-activedescendant` when navigating the options in an autocomplete, etc.)*
* ...and many other concerns.

If you're using Tailwind UI with React or Vue, all of this complexity is handled for you automatically by [Headless UI](https://headlessui.dev/), but if you are providing your own JS, **it is up to you to follow accessibility best practices when adding interactive behavior.**

To learn more about building accessible UI components, we recommend studying the [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices/) published by the W3C.

### Dynamic classes

When an element needs different classes applied based on some state *(like a toggle being on or off)*, we list the classes for each state in a comment directly above the element:

```html

```

**The HTML we provide is always pre-configured for one of the defined states**, and the classes that you need to change when switching states are always at the very beginning of the class list so they are easy to find.

As an example, to adapt this HTML for [Alpine.js](https://github.com/alpinejs/alpine), you can conditionally apply the correct classes using the `:class` directive based on some state you've declared in `x-data`:

```html

```

*We've included a basic click handler here to demonstrate the general idea, but **please reference the [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices/) when building components like this** to ensure you implement all of the necessary keyboard interactions and properly manage any required ARIA attributes.*

### Transitions

For elements that should be dynamically shown or hidden *(like the panel on a dropdown)*, we include the recommended transition styles in a comment directly above the dynamic element:

```html

```

As an example, to adapt this HTML for [Alpine.js](https://github.com/alpinejs/alpine) you would use the [`x-transition`](https://github.com/alpinejs/alpine#x-transition) directive to apply the right classes at each point in the transition lifecycle:

```html

```

*We've included a basic click handler here to demonstrate the general idea, but **please reference the [WAI-ARIA Authoring Practices](https://www.w3.org/TR/wai-aria-practices/) when building components like this** to ensure you implement all of the necessary keyboard interactions and properly manage any required ARIA attributes.*

### Creating partials/components

Since the vanilla HTML examples included in Tailwind UI can't take advantage of things like loops, there is a lot of repetition that wouldn't actually be there in a real-world project where the HTML was being generated from some dynamic data source. We might give you a list component with 5 list items for example that have all the utilities duplicated on each one, whereas in your project you'll actually be generating those list items by looping over an array.

When adapting our examples for your own projects, we recommend creating reusable template partials or JS components as needed to manage any duplication.

Learn more about this in the ["Extracting Components" documentation](https://tailwindcss.com/docs/extracting-components#extracting-html-components) on the Tailwind CSS website.

- - -

## Resources & assets

### Icons

All of the icons we use in Tailwind UI come from [Heroicons](https://heroicons.com/), which is a free MIT-licensed icon set we designed and developed ourselves when we started working on Tailwind UI.

### Images

Images in Tailwind UI come almost exclusively from [Unsplash](https://unsplash.com/). It's a great resource if you need freely-usable photography for your projects.

### Illustrations

Some of the examples in Tailwind UI use illustrations from the free [Lucid Illustrations](https://lucid.pixsellz.io/) pack by [Pixsellz](https://www.pixsellz.io/). You can grab the full set of illustrations and check out their other design resources on [their website](https://www.pixsellz.io/).

### Figma assets

We've discontinued the Figma assets so we can focus our efforts on building more great examples with Tailwind CSS.

We used to provide Figma assets for Tailwind UI, but they were just an absolutely enormous amount of work to maintain and very few people were using them. We've made the really hard decision to discontinue them so we can spend more time on the actual code which is where we think we can provide the most value.

Customers of Tailwind UI can download the final Figma file we released, but please note **the Figma file does not receive updates** and does not contain any examples released after July 14, 2021.