# Welcome! 🦗

## File Downloads
All GH files will be available for download. Follow [the links](https://github.com/aarcThom/aarc-wiki/blob/main/gh_definitions/01_basic_definition.gh) provided with each page of instruction to download the proper file. Once you're on the linked page, click the *raw download* button as shown in a green rectangle below to download the `.gh` file.

<figure markdown>
  ![Basic Definition](img/first-def/02_download.png){ width="850" }
  <figcaption>Click the button in the green rectangle!</figcaption>
</figure>

## Markdown Conventions

These documents use a few textual conventions to help with readability.

### Grasshopper Components
`Inline Code Text` refers to the name of a specific Grasshopper component. For example,  the component below would be referred to as `Sphere`.

<figure markdown>
  ![Basic Definition](img/first-def/01_a_geo.png){ width="850" }
</figure>

### Component Inputs and Outputs (Parameters)
**Bolded Text** refers to the parameters of a component. For example, in the image above, we see **Base** and **Radius** on the input, and **Sphere** on the output of `Sphere`.

### Component Options
*Italicized Text* refers to right click options found within the components themselves. For example, in the image below *Expression* would be italicized.

<figure markdown>
  ![Basic Definition](img/first-def/6a_expression.png){ width="850" }
</figure>

### Mouseclicks and Shortcuts
Mouse clicks will be represented by ++"rmb"++ for a right-click, and ++"lmb"++ for a left-click. Shortcuts will represented by their key combos. For example, ++ctrl+c++ for copy.

### Admonitions
Important points will be formatted like so:

!!! Tip "Parameters & Components - What are they?"
    All the little 'nodes' that make up a Grasshopper definition (script) are called *components*. *Parameters* are a class of component that either reference data from Rhino, reference data from outside of Rhino / Grasshopper, or, as in this case, reference user input.

Common beginner traps will be formatted like so:

!!! Warning "Always X!"
    The input Expression field can only ever contain one variable, X. If you need a more complex expression, you can always build it up outside of an input from components found in the *Maths* tab.