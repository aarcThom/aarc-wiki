# Interacting with Rhino and Basic Geometrical Concepts

See [this Rhino file](https://github.com/aarcThom/aarc-wiki/blob/main/gh_definitions/02_refRhino_geoConcepts.3dm) and [this Grasshopper file](https://github.com/aarcThom/aarc-wiki/blob/main/gh_definitions/02_refRhino_geoConcepts.gh).

In this example, we will be looking at how we can place a tree, made with Rhino, on a surface, lofted in Grasshopper from Rhino curves. We will explore the the following important concepts:

1.  **Referencing Rhino geometry**
2.  **Surface UVs**
3.  **Points**
4.  **Vectors**
5.  **Planes**

Our grasshopper definition looks like this:

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/__definition.png){ width="850" }
</figure>

Our Rhino viewport will look like this:

<figure markdown>
  ![Basic Definition](../img/02_ref_geo//__rhino_view.png){ width="850" }
</figure>

## 01 / 02 - Referencing Rhino Geometry

For the last definition we looked at, we created all of our geometry within Grasshopper itself, but usually it's easier to create geometry in Rhino and then bring it into Grasshopper. This is called **referencing geometry**.

For an in-depth look at referencing Rhino geometry, see [this thorough write-up on Hopific](https://hopific.com/how-to-reference-objects-in-grasshopper/#:~:text=Referencing%20geometry%20is%20oftentimes%20the,first%20group%20called%20'Geometry'.).


## 03 - Interacting with Rhino Geometry

When you reference Rhino geometry in Grasshopper, you are creating a live link to that geometry. Changes that are made in Rhino will automatically update the referenced geometry in Grasshopper. Any downstream impacts within the GH definition will also update in real time.

In our case, after referencing our curves, we can move them around, scale them, adjust their control points, etc. and all changes will be reflected in Grasshopper.

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/03a_ref_crvs.gif){ width="850" }
</figure>

However, there are limitations to this live link. Grasshopper references geometry per Rhino object. If you were to split one of your referenced curves into two, Grasshopper would lose the link to the two resultant curves, as technically, two new objects are created in Rhino. In such a case, you will need to re-reference the new geometry.

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/03b_split_crv.gif){ width="850" }
</figure>


## 04 - Surface UV Coordinates

In Rhino, we are used to working with coordinates. In particular, we are used to working in a 3D Cartesian coordinate system composed of X values and Y values (the horizontal coordinates) and a Z value (the vertical coordinate). If we wanted to represent some points on our lofted surface as X,Y,Z coordinates, it would look something like:

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04a_cartesian.png){ width="850" }
</figure>



