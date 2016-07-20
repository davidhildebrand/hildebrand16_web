---
title: outline
layout: default
---

Hildebrand16 Guide
===================

###**Introduction**

The goal of this guide is to familiarize users with the Hildebrand16 electron micrograph (EM) dataset and the tools used to serve it. The dataset is a collection of serial-section electron microscopy image volumes acquired at different resolutions that collectively encompass the anterior quarter of one 5.5 days post-fertilization larval zebrafish.

We generated this dataset to study the anatomy of the larval zebrafish brain--which is included in its entirety--and peripheral nervous system. Toward this goal, we reconstructed and annotated some features of the nervous system, namely myelinated neuronal processes, which are also available for browsing or analysis. Many non-neuronal tissues are captured in the dataset.

----------

###**Software**

All electron micrographs and reconstructions are hosted using the [Collaborative Annotation Toolkit for Massive Amounts of Image Data (CATMAID)](http://catmaid.org/). CATMAID is designed to aid in the annotation and sharing of image datasets. This guide serves as an initial reference to help users navigate the CATMAID instance we use to host the dataset. For a more thorough understanding of the software and its functionality, please visit the [CATMAID documentation page](http://catmaid.readthedocs.org/).
Note that using the Google Chrome browser for interacting with CATMAID is highly recommended.

----------

###**Getting started**


####**Accessing**

Clicking on either the “[View data](http://hildebrand16.neurodata.io/catmaid/?pid=3&zp=537540&yp=351910&xp=303051&tool=navigator&sid0=2&s0=4)” or the "[View data with reconstructions](http://hildebrand16.neurodata.io/catmaid/?pid=3&zp=537540&yp=351910.65&xp=303051.44999999995&tool=tracingtool&sid0=2&s0=4)" link on the main page will immediately transport you into CATMAID.
The colored dots visible in the "View data with reconstructions" option are positions where a reconstructed object such as a myelinated neuron intersects with the current transverse section.

| View data        | View data and reconstructions |
|:----------------:|:-----------------------------:|
| ![alt text][Vd]  | ![alt text][Vdar]             |

[Vd]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/View_data.png "View data"
[Vdar]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/View_data_and_reconstructions.png "View data and reconstructions"


####**Navigating**

Across the top of the page in CATMAID, you will see a toolbar. The toolbar provides useful information about the current view and contains various tools with which to interact with the data.


#####**Orienting**

Displayed in the toolbar are the current position, section number, and zoom level.
The current position is defined by the center of the field of view (x, y; in nm from the top left corner) and the section number (z-index; each ~60 nm):

![alt text][Tbl]

The zoom level for the field of view can be set to visualize the full extents of the transverse section at low resolution or a restricted field of view at high resolution:

![alt text][Tbz]

The approximate resolution associated with each zoom level is:

| Zoom level | Resolution              |
|------------|-------------------------|
| 5          | 1.8 μm/px               |
| 4          | 0.9 μm/px               |
| 3          | 451.2 nm/px             |
| 2          | 225.6 nm/px             |
| 1          | 112.8 nm/px             |
| 0          | 56.4 nm/px              |
| -1         | 28.2 nm/px              |
| -2         | 14.1 nm/px <sup>†</sup> |
| -3         | 7.05 nm/px <sup>†</sup> |

<sup>†</sup>Artificially upsampled. The actual resolution of raw data is 18.8 nm/px within most brain regions and 56.4 nm/px outside the brain.

[Tbl]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_location.png "Toolbar location"
[Tbz]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_zoom.png "Toolbar zoom"


#####**Panning**

To pan around the current transverse section, click the *pan tool button* on the toolbar:

![alt text][Tbp]

Holding down your *left mouse button* while dragging will pan your view.
Alternatively, if you have a *middle mouse button*, hold it down when any tool is selected and drag to pan your view.

[Tbp]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_pan.png "Toolbar pan"


#####**Viewing reconstructions**

To view existing neuron reconstructions, click the *tracing tool button* on the toolbar:

![alt text][Tbt]

Colored dots will appear on top of the EM data:

![alt text][Vdar]

Each dot is a single node indicating where the current section intersects with a directed [polyline](https://en.wikipedia.org/wiki/Polyline) (or treeline) annotation used to represent the morphology of a particular neuron.
Clicking the *spacebar key* toggles between viewing reconstructions as overlays on the data and a data-only view.
Any given node (and, thus, neuron) can be selected by hovering over it with the mouse cursor and pressing the *'g' key*.

| No node selected   | Node selected (green) |
|:------------------:|:---------------------:|
| ![alt text][Nns]  | ![alt text][Ns]        |

[Tbt]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_tracing.png "Toolbar tracing"
[Nns]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Node_noneselected.png "Nodes, none selected"
[Ns]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Node_selected.png "Node selected"


#####**Viewing tags (meta-information)**

Tags are meta-information associated with individual nodes. To view the tags associated with individual nodes, click the *tag tool button* on the toolbar or press the *'7' key*:

![alt text][Tbtg]

Tags are useful for indicating specific features such as the location of a soma (which we mark as the center of the nucleus) or the position where a neuronal process becomes myelinated.

| Without tag view   | With tag view         |
|:------------------:|:---------------------:|
| ![alt text][Tswo]  | ![alt text][Tsw]      |
| ![alt text][Tmwo]  | ![alt text][Tmw]      |

[Tbtg]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_tags.png "Toolbar tags"
[Tmwo]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Tag_myelinated_without.png "Myelination event without tag"
[Tmw]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Tag_myelinated_with.png "Myelination event with tag"
[Tswo]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Tag_soma_without.png "Soma without tag"
[Tsw]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Tag_soma_with.png "Soma with tag"

#####**Finding reconstructed neurons**

Included in the database are several reconstructions, including all myelinated neurons that we could find. Some of these neurons are named or annotated and can be found with the CATMAID search functions.
To search by name or annotation, click the *neuron/annotation search button* on the toolbar or press the *'/' key*:

![alt text][Tbns]

This action will add a new panel to your CATMAID session. In the new panel, there are fields for name or annotation searching. You can, for example, search for the Mauthner neurons by name or annotation by typing in 'mauthner':

![alt text][NAs]

If the search result type is 'annotation', clicking on it will list neurons with that annotation.
If the search result type is 'neuron', clicking on it will select the neuron as active and color its nodes in the main panel.
Additionally, checkboxes in the table can select results for performing other functions, such as adding annotations or adding the reconstructions to a three-dimensional (3D) view.

[Tbns]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_neuronsearch.png "Neuron/annotation search"
[NAs]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Neuron_search.png "Neuron/annotation search"

Additional searchable annotations currently include:

| Annotation                  | Description                                                       |
|----------------------------:|:------------------------------------------------------------------|
| lateral_line                | An element of the lateral line (neuromast or afferent)            |
| left                        | Soma (or majority if no soma) is on the left side                 |
| Mauthner                    | A Mauthner neuron                                                 |
| motor                       | Directly innervates a muscle (i.e., motor neuron)                 |
| myelinated                  | Some portion is myelinated                                        |
| not_neuronal                | Not a neuron                                                      |
| neuromast                   | Marks the position of a neuromast                                 |
| neuromast_afferent          | A lateral line afferent that innervates a neuromast               |
| nucMLF                      | Member of the nucleus of the medial longitudinal fasciculus       |
| peripheral                  | Part of the peripheral nervous system                             |
| PLLn                        | Travels through a peripheral lateral line nerve (PLLn)            |
| putative_spinal_projection  | May project to the spinal cord                                    |
| right                       | Soma (or majority if no soma) is on the right side                |
| saccule                     | Marks a saccule                                                   |
| sensory                     | Directly innervates a sensory organ                               |
| unmyelinated                | No known portion is myelinated                                    |
| unknown                     | Name or class of neuron is unknown or not yet labeled             |
| utricle                     | Marks a utricle                                                   |


#####**Viewing reconstructions in 3D**

Visualizing the morphology of a reconstructed neuron benefits from 3D renderings. CATMAID includes a 3D viewer for this purpose.
To begin the process of rendering in 3D, click on the *3D view button*:

![alt text][Tb3D]

This will add two new panes, including the 3D viewer and a selection table:

![alt text][V3Dp]

The currently active skeleton or results from searching for a particular neuron or class of neurons (i.e., by annotation) can be added to the 3D viewer by using the drop-down menu and append button in the selection pane.
In the search results case, neurons can be added to the 3D view by checking the boxes next to result(s) of interest, selecting 'Neuron Search 1' in the drop-down menu, and clicking the *Append* button:

![alt text][STa]

For both the left and right Mauthner neurons searched for previously, you will see a rendering of two neurons within a bounding box (red outline) defined by the image stack and a floor (white mesh):

![alt text][V3Dm]

To rotate the view, click and drag the *left mouse button*.
To zoom in or out, scroll your *mouse wheel*.
To pan within the 3D viewer, click and drag the *right mouse button*.
Several additional view and color settings are available in the 3D view and selection panes.

For example, it can be helpful to change the color associated with different neurons in the 3D viewer. The *Colorize* button in the Selection Table randomly assign colors to all neurons selected in the selection table:

![alt text][STc]

It is also possible to search for a particular neuron or class of neurons by name or annotation. Clicking on the *Batch Color* button will label the selected subset in the Selection Table. Alternatively, the desired color can be specified for a single neuron by clicking on its *color* button in the appropriate Selection Table row:

![alt text][STsc]

Identifying the location of the active node can be accomplished by checking the *Active node* setting in the 3D viewer View Settings panel:

![alt text][V3Dans]

With this setting, the 3D viewer will update a green sphere to the location of the active node as one interacts with the database:

![alt text][V3Dani]

[Tb3D]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Toolbar_3Dview.png "Toolbar 3D view"
[V3Dp]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/View_3D.png "3D view pane"
[STa]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Selection_append.png "Selection append"
[V3Dm]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/View_3D_mauthner.png "3D view pane with Mauthner neurons"
[STc]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Selection_colorize.png "Selection colorize"
[STsc]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Selection_searchcolor.png "Selection search and color"
[V3Dans]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/View_3D_activenodeset.png "3D view pane active node setting"
[V3Dani]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/View_3D_activenodeinteractive.png "3D view pane active node interactivity"

#####**Different resolutions**

The database includes overlapping image stacks acquired at different resolutions. For a g


----------


iven section (z-index), images acquired at different resolutions are treated as layers. The higher resolution images are placed on top of--and obscuring the view of--the lower resolution images.

Click the *layer controls button* in the bottom right corner of the main pane to access options associated with each image stack layer:

![alt text][LCb]

Layer controls allow you to remove a particular image stack or resolution from view, change layer opacity, or alter display settings:

![alt text][LC]

[LCb]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Layer_controls_button.png "Layer controls button"
[LC]: https://github.com/davidhildebrand/hildebrand16/raw/master/images/Layer_controls.png "Layer controls"


----------

###**Additional help**

Pressing the *'F1' key* will bring up a CATMAID help window pane that reveals commands available with any given tool. Note that some CATMAID tools will not function properly without additional access. For example, annotating additional features is not currently publicly available. However, we are happy to provide access for those who wish to create additional annotations.

----------
Last updated on 2016-06-14 by David Hildebrand
<!--se_discussion_list:{"h41SbNlsqb3mtPdQeOIdtotf":{"selectionStart":14629,"type":"conflict","selectionEnd":14639,"discussionIndex":"h41SbNlsqb3mtPdQeOIdtotf"}}-->
