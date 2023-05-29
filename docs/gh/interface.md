# Grasshopper Interface
First things, first. To open Grasshopper type  ```grasshopper``` into your Rhino command line, or simply click the 🦗 icon in the standard tab.

## A First Look
The window that pops up should look something like the image below. Note that your window may also be overlaid with the tutorials file window. You can safely close this window as those tutorials are also stored in the 🦗 help tab.

The image below outlines the main areas of the user interface. Each of these areas are elaborated in the following sections. Click on the tabs below to scroll through descriptions of the sub-menus and functionalities of the 🦗 UI.

<figure markdown>
  ![Image title](../img/intro-interface/gh-interface-interface.png){ width="850" }
  <figcaption>Grasshopper Interface</figcaption>
</figure>

## Main Menu Bar
=== "Intro"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--intro.png){ width="850" }
    </figure>

    The main menu bar is similar to other programs you have encountered using windows.

=== "File tab"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--filetab.png){ width="850" }
    </figure>

    !!! Warning
        Grasshopper has a tendency to freeze and/or crash while you are learning how to use it. Save often using the ```Save``` command under the file tab, or press ++ctrl+s++.

    Open one of the tutorial files under ```Help --> Tutorial Files``` and try both the ```export quick image``` and ```Export Hi-Res Image``` commands. These can be useful for sharing your work with others. I wouldn't encourage you to include the diagrams on studio presentation boards however. Most often reviewers will not be able to make heads or tails of the spaghetti like image!

    We will return to ```special folders``` when we look at installing plugins, but for now just know its there.

    Finally, the ```new document```, ```open document```, ```recent files``` and ```close``` will behave as expected.

=== "Edit tab"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--edittab.png){ width="850" }
    </figure>

    !!! Tip
        Most non-mac computers will be able to use the common shortcuts ++ctrl+c++ for copy, etc. Users with mac laptops *but running Rhino on Windows* often have to use the commands located in ```edit``` in order to copy, paste, delete.

    Grasshopper's ```copy```, ```paste```, ```delete```, ```undo```, ```redo```, ```select all```, and ```deselect all``` will function as expected. Most likely, you will end up using the shortcuts. For example, +++ctrl+c+++ for copy. We will get to what exactly we will be copying in the next section.

    The other commands will be covered in later sections.

=== "View tab"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--viewtab.png){ width="850" }
    </figure>

    The view tab primarily deals with the view of the interface menus itself. Feel free to play around with settings, but know that these tutorials use default settings. 

    The one section that you may find useful is ```zoom```. This section allows you to zoom to different areas of your definition and the canvas.

=== "Display tab"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--displaytab.png){ width="850" }
    </figure>

    The display tab primarily deals with the was grasshopper objects are drawn in Rhino and the way Grasshopper components are drawn on the canvas.

    !!! Tip
        For all of these tutorials we will use the default display setting minus one change. I would encourage you to enable ```Draw Full Names```. This setting will render full names on your GH components. This is especially helpful for learning what each component does.
    
    Return to the settings after completing the **Grasshopper Basics** section. You may find that you prefer different display settings. For now, you can leave all other settings as default.

=== "Solution tab"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--solutiontab.png){ width="850" }
    </figure>

    The solution tab primarily deals with the *Grasshopper solver*. As data flows through your components, you can use the options in this tab to pause the solver and save states of flows.

    This section also allows you to disable, preview, and bake (bring into Rhino) the outputs of components.

    You will find that this tab is rarely used, so know it's there, but don't be surprised if you never open it again.

=== "Help tab"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--helptab.png){ width="850" }
    </figure>

    Now, this is an important tab!

    !!! diy "Try it for yourself!"
        While we're here. Take some time to go through the ```tutorial files```. Don't worry if they don't totally make sense.

    The ```grasshopper support``` command will take you to the [Mcneel Grasshopper Forum](https://discourse.mcneel.com/c/grasshopper/2). It's worth searching this forum for a question you may have. Further, make an account and ask you own question if you can't find an answer!

    The ```Online Reference``` command will take you to the [Grasshoper Components Documentation](http://grasshopperdocs.com/) where you will find notes *on every single component.*

    !!! Tip "Google is your friend"
        I would encourage you to simply google "grasshopper" plus whatever problem you are trying to solve. Google is your friend.

    !!! Tip "ChatGPT is your unreliable (but still useful) friend"
        You can also try asking [ChatGPT](https://chat.openai.com/) to describe a basic component flow and even generate a rudimentary diagram.

        Try phrasing you question as 
        
        ```I'm using Rhino 3D grasshopper. What components could I use to make a <insert your goal here>? Include a diagram with your answer.```

        You will get a step by step instruction set with a diagram that looks like this:
        ```
          [Curve]   [Curve Length]  [Divide Curve]   [Point On Curve]
             |             |                |                |
             +-------------+----------------+----------------+
                                   |
                             [Offset Curve]
                                   |
                                   +-------+
                                           |
                                        [Loft]
                                           |
                                           +------+
                                                   |
                                          [Sweep 1 Rail]
                                                   |
                                             [Staircase Geometry]
        ```
        Pretty cool!

        In my testing, its answer are *generally* correct in approach but will contain smaller errors. This may be a good way to brainstorm but do not use ChatGPT as a crutch, especially when you are first learning.

=== "File browser"

    <figure markdown>
    ![Image title](../img/intro-interface/interface-menu/int--filebrowser.png){ width="850" }
    </figure>

    The ```file browser``` appears after you have opened at least one GH file. When you have more than one GH file open, you can switch between them using the ```File browser``` located on the right hand side of the main menu bar. You can also close files from the browser.
