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

### UV Coordinates - Overview

In Rhino, we are used to working with coordinates. In particular, we are used to working in a 3D Cartesian coordinate system composed of X values and Y values (the horizontal coordinates) and a Z value (the vertical coordinate). If we wanted to represent some points on our lofted surface as X,Y,Z coordinates, it would look something like:

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04a_cartesian.png){ width="850" }
</figure>

This X,Y,Z coordinate system is great for a lot of things, but gets a bit clunky when we want to describe a position on the surface itself. For example, the above image shows our center point of the surface as **(28, 148, 14)** but wouldn't it be much easier if we could describe our center point as **(0.5, 0.5)**? This is where a **UV coordinate system** comes into play. We can describe points on the surface with a **UV coordinate system** like so:

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04b_UV.png){ width="850" }
</figure>

Since we are only working with U and V dimensions, we drop any notion of elevation. In other words, this coordinate system does not describe the waviness of the surface but only the position *within* the surface. If you want to form a mental image, imagine a gridded blanket where you consider the lines in one direction U, and the lines in the other direction, V. Those lines still describe the same positions on the blanket, even if they're wrapped around a dog!

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04D_UVblanket.png){ width="850" }
</figure>

If you want to see those wavy lines in the Rhino screen, you can also run the command, `_ExtractIsocurve`.

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04c_uvlines.gif){ width="850" }
</figure>

### UV Coordinates - Reparameterization

In Grasshopper it is really useful to describe surfaces with UV coordinates ranging from 0 to 1 in both directions. It ensures that whatever wavy surface we pass into a component, we will be able to describe a location on that surface.

If we look back to [the provided file's group 4](https://github.com/aarcThom/aarc-wiki/blob/main/gh_definitions/02_refRhino_geoConcepts.gh) you can see that we're using the `MD Slider` to define a UV coordinate which we feed into the **Point** input of `Evaluate Surface`.

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04e_param.png){ width="850" }
</figure>

This makes sense so far given what we've learned about UV coordinates, but why do we only see a little wiggle when we move the `MD Slider` around? We see this behavior because Grasshopper, by default doesn't assign a range of 0 --> 1 to the UV directions of a surface. The UV values by default are based on XYZ values, or something like that, I think ... I've represented these random upper limits of UV with 1234 in the image below. In other words, it doesn't really matter what your initial UV system is, because you always want good old predictable 0 to 1! 

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04e_unparammarkup.gif){ width="850" }
</figure>

To convert our surface's UV ranges to 0 --> 1, we have to ++"rmb"++ the **Surface** input of `Evaluate Surface` and click *Reparameterize*. You will know see that UV coordinates output by `MD Slider` return the location on the surface that we would expect. Get used to *reparameterizing* surfaces all the time in Grasshopper!

<figure markdown>
  ![Basic Definition](../img/02_ref_geo/04f_reparam.gif){ width="850" }
</figure>