# Photoshop Boilerplate
A guide to help designers create more logical and coherent designs.
## Table of Contents
- [Introduction](#introduction)
- [Framework First](#framework-first)
- [Approach Overview](#approach-overview)
    - [Guides](#guides)
    - [Naming (Files, Layers, Layer Compositions)](#naming-files-layers-layer-compositions)
    - [Layer Groups](#layer-groups)
    - [Smart Objects](#smart-objects)
    - [Adjustment Layers](#adjustment-layers)
    - [Layer Compositions](#layer-compositions)
    - [Folder Structure](#folder-structure)

## Introduction
The Photoshop Boilerplate has been created to help streamline web-based design projects, creating a greater synergy between design and development, and serve as a practice guide to aid collaborative work. No more lazy PSDs with rasterized components and unnecessary grid obstructions. This project is about creating clean, pixel perfect designs that translate perfectly to development to be loved by all.

### Things to note
* This guide assumes competency in Photoshop and some knowledge of Front End Development.
* Each project will inevitably vary from this boilerplate, it's to be used as a general best-practice guide. So yes, you can deviate from the instructions given here!
* These guidelines and recommendations are largely informed by preference/opinion ... but I'm definitely right.
* The primary purpose for these boilerplate projects is to demonstrate working examples of a methodology.

## Framework First
Each front end framework has its own derivatives of component class names and structures, which needs to be duly noted as this will dictate how we name our layers and influence the naming convention we adopt. That said, wherever it is deemed logical we will be adopting the [BEM naming convention], as this adds logical context to class/layer names. 

For ease I have created a Photoshop Boilerplate for the following frameworks:

* [Foundation for Sites]
* [Bootstrap]
* Creative Little UI Kit

Whilst the Creative Little UI Kit does not have a public release this has been included as it demonstrates a best-practice BEM approach in naming conventions in its entirety.

## Approach Overview
Much of the following are basic best-practices for Photoshop etiquette. I will try to keep instructions brief and concise.

### Guides
Using our Framework First approach allows us to setup guides consistent with the frameworks grid, and with vertical guides we shouldn't really need to deviate from this at all. Create guides efficiently with an extension such as [GuideGuide].

### Naming (files, layers, layer compositions)
* Follow the [BEM naming convention] where possible
* All lowercase names
* No spaces, hyphenate instead
* Use American English (ie. use *color* instead of colour)
* Please no `Layer 2 copy` filenames, that stuff hurts my soul. Try and keep an eye on those pesky duplicates and name them contextually
* **File and layer name specific rules:**
  * Follow the order of `[html element],[class]` - with HTML element optional (mostly applicable with form elements, or HTML5 tags such as article, aside etc.)
  * If you'd like to use a descriptive name (ie. `header`, `hero` etc.) this should be prefixed with `#` to denote this is a comment/descriptive name
* **Paragraph Styles and Character Styles specific rules:**
  * Follow the order of either `[html element]@[size]` or `[class]@[size]` depending on what is most appropriate
  
### 3. Paragraph Styles and Character Styles
* Use the naming convention outlined above
* Be aware that each individual PSD have independent Paragraph and Character styles from each-other, but it is possible to import styles to maintain consistency across every component and page layout

### Layer Groups
* Use layer groups generously to organise the project into logical sections
* Consider grouping each natural row, to make navigating the PSD easier

### Smart Objects
Groups are nice but Smart Objects are powerful, use them as much as possible.
* Make *all* components into PSD-based Smart Objects, ***and link them*** (folder structure outlined below)
* Avoid embedded Smart Objects, always prefer linked
* Insert all assets as *linked* Smart Objects (photos, svgs etc)

### Adjustment Layers
Don't change originals, use adjustment layers so effects can be toggled, edited or removed.

### Layer Compositions
* Use to display different page states or interactivity (such as hover states)
* Use within components to create modifiers. For example, a hero which changes content accordingly to each page would be one PSD file (component) with a layer composition for each variant

### Folder Structure
``` ruby
[framework]/
+-- assets
    +-- colors
    +-- icons
    +-- logo
    +-- misc
    +-- photography
+-- components
    +-- large
    +-- medium
    +-- small
+-- layouts
```
#### Breakdown
* `assets` is the primary folder for any linked items used in the project
  * `colors` contains each colour defined within the project. Filenames should match variables later created in SCSS
  * `icon` contains any icons used throughout the project, preferably SVG
  * `logo` contains the main brand logo (and potentially partner logos), preferably SVG
  * `misc` contains anything else
  * `photography` self explanatory
* `components` is the primary folder for any linked smart objects used throughout the project. Within this folder should be a sub-folder for each viewport size you'll be producing designs for
  * `large` in our example we are using *large* as a non device specific size
  * `medium` in our example we are using *medium* as a non device specific size
  * `small` in our example we are using *small* as a non device specific size
* `layouts` is where all page layout PSD's are located.

### Colour Variables (Optional and Experimental)
Photoshop does not unfortunately support colour variables, which has been a huge downfall as updating a colour to be slightly lighter after a client request can be a very length exercise. To counter this I've adopted a technique recently which does work around this, but it is quite restrictive - so I'm still unsure it's something to permanently adopt.

#### The solution
In the boilerplate I have made careful use of linked Smart Objects (using colours from `assets/color`) and layer masks accordingly. In theory this means if we update the Smart Object, it will be updated globally throughout the project.

#### Known issues
* Photoshop does not auto-update Smart Objects even or prompt on file open (as you might expect, similar to InDesign). To work around this I have created an action to     *Update All Linked Smart Objects* which can be run as a batch command on the project. As there are instances of nesting there will however likely be instances where files must be manually updated.

### Todos

 - Restructure this readme so it is easier to follow
 - Create Bootstrap files
 - Create Creative Little UI Kit design

License
----

Copyright (c) 2016 Creative Little Dots. MIT Licensed, see [LICENSE] for details.

[//]: # 
   [BEM naming convention]: <http://getbem.com/naming/>
   [Foundation for Sites]: <http://foundation.zurb.com/sites.html>
   [Bootstrap]: <http://getbootstrap.com>
   [GuideGuide]: <http://guideguide.me>
   [License]: <https://github.com/creativelittledots/photoshop-boilerplate/blob/master/LICENSE.md>