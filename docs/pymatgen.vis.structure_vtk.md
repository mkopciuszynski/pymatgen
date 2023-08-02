---
layout: default
title: pymatgen.vis.structure_vtk.md
nav_exclude: true
---

# pymatgen.vis.structure_vtk module

This module contains classes to wrap Python VTK to make nice molecular plots.


### _class_ pymatgen.vis.structure_vtk.MultiStructuresInteractorStyle(parent)
Bases: `StructureInteractorStyle`

Interactor for MultiStructureVis.


#### keyPressEvent(obj, event)

### _class_ pymatgen.vis.structure_vtk.MultiStructuresVis(element_color_mapping=None, show_unit_cell=True, show_bonds=False, show_polyhedron=False, poly_radii_tol_factor=0.5, excluded_bonding_elements=None, animated_movie_options={'looping_type': 'restart', 'number_of_loops': 1, 'time_between_frames': 0.1, 'time_between_loops': 1.0})
Bases: `StructureVis`

Visualization for multiple structures.


* **Parameters**


    * **element_color_mapping** – Optional color mapping for the elements,
    as a dict of {symbol: rgb tuple}. For example, {“Fe”: (255,
    123,0), ….} If None is specified, a default based on
    Jmol’s color scheme is used.


    * **show_unit_cell** – Set to False to not show the unit cell
    boundaries. Defaults to True.


    * **show_bonds** – Set to True to show bonds. Defaults to True.


    * **show_polyhedron** – Set to True to show polyhedrons. Defaults to
    False.


    * **poly_radii_tol_factor** – The polyhedron and bonding code uses the
    ionic radii of the elements or species to determine if two
    atoms are bonded. This specifies a tolerance scaling factor
    such that atoms which are (1 + poly_radii_tol_factor) \* sum
    of ionic radii apart are still considered as bonded.


    * **excluded_bonding_elements** – List of atom types to exclude from
    bonding determination. Defaults to an empty list. Useful
    when trying to visualize a certain atom type in the
    framework (e.g., Li in a Li-ion battery cathode material).


    * **(****)** (*animated_movie_options*) – Used for moving.



#### DEFAULT_ANIMATED_MOVIE_OPTIONS(_ = {'looping_type': 'restart', 'number_of_loops': 1, 'time_between_frames': 0.1, 'time_between_loops': 1.0_ )

#### apply_tags()
Apply tags.


#### display_help()
Display the help for various keyboard shortcuts.


#### display_info(info)

* **Parameters**

    **info** (*str*) – Information.



#### display_warning(warning)

* **Parameters**

    **warning** (*str*) – Warning.



#### erase_info()
Erase all info.


#### erase_warning()
Remove warnings.


#### set_animated_movie_options(animated_movie_options=None)

* **Parameters**

    **(****)** (*animated_movie_options*) –



#### set_structure(structure: [Structure](pymatgen.core.structure.md#pymatgen.core.structure.Structure), reset_camera=True, to_unit_cell=False)
Add a structure to the visualizer.


* **Parameters**


    * **structure** – structure to visualize


    * **reset_camera** – Set to True to reset the camera to a default
    determined based on the structure.


    * **to_unit_cell** – Whether or not to fall back sites into the unit cell.



#### set_structures(structures: Sequence[[Structure](pymatgen.core.structure.md#pymatgen.core.structure.Structure)], tags=None)
Add list of structures to the visualizer.


* **Parameters**


    * **structures** (*list**[**Structures**]*) – structures to be visualized.


    * **(****)** (*tags*) – List of tags.



### _class_ pymatgen.vis.structure_vtk.StructureInteractorStyle(parent)
Bases: `object`

A custom interactor style for visualizing structures.


#### keyPressEvent(obj, event)

#### leftButtonPressEvent(obj, event)

#### leftButtonReleaseEvent(obj, event)

#### mouseMoveEvent(obj, event)

### _class_ pymatgen.vis.structure_vtk.StructureVis(element_color_mapping=None, show_unit_cell=True, show_bonds=False, show_polyhedron=True, poly_radii_tol_factor=0.5, excluded_bonding_elements=None)
Bases: `object`

Provides Structure object visualization using VTK.

Constructs a Structure Visualization.


* **Parameters**


    * **element_color_mapping** – Optional color mapping for the elements,
    as a dict of {symbol: rgb tuple}. For example, {“Fe”: (255,
    123,0), ….} If None is specified, a default based on
    Jmol’s color scheme is used.


    * **show_unit_cell** – Set to False to not show the unit cell
    boundaries. Defaults to True.


    * **show_bonds** – Set to True to show bonds. Defaults to True.


    * **show_polyhedron** – Set to True to show polyhedrons. Defaults to
    False.


    * **poly_radii_tol_factor** – The polyhedron and bonding code uses the
    ionic radii of the elements or species to determine if two
    atoms are bonded. This specifies a tolerance scaling factor
    such that atoms which are (1 + poly_radii_tol_factor) \* sum
    of ionic radii apart are still considered as bonded.


    * **excluded_bonding_elements** – List of atom types to exclude from
    bonding determination. Defaults to an empty list. Useful
    when trying to visualize a certain atom type in the
    framework (e.g., Li in a Li-ion battery cathode material).


Useful keyboard shortcuts implemented.

    h : Show help
    A/a : Increase/decrease cell by one unit vector in a-direction
    B/b : Increase/decrease cell by one unit vector in b-direction
    C/c : Increase/decrease cell by one unit vector in c-direction
    # : Toggle showing of polyhedrons
    - : Toggle showing of bonds
    [ : Decrease poly_radii_tol_factor by 0.05
    ] : Increase poly_radii_tol_factor by 0.05
    r : Reset camera direction
    o : Orthogonalize structure
    Up/Down : Rotate view along Up direction by 90 clock/anticlockwise
    Left/right : Rotate view along camera direction by 90
    clock/anticlockwise


#### add_bonds(neighbors, center, color=None, opacity=None, radius=0.1)
Adds bonds for a site.


* **Parameters**


    * **neighbors** – Neighbors of the site.


    * **center** – The site in the center for all bonds.


    * **color** – Color of the tubes representing the bonds


    * **opacity** – Opacity of the tubes representing the bonds


    * **radius** – Radius of tube s representing the bonds



#### add_edges(edges, type='line', linewidth=2, color=(0.0, 0.0, 0.0))

* **Parameters**


    * **(****)** (*linewidth*) – List of edges


    * **(****)** –


    * **(****)** – Width of line


    * **color** (*nd.array/tuple*) – RGB color.



#### add_faces(faces, color, opacity=0.35)
Adding face of polygon.


* **Parameters**


    * **(****)** (*color*) – Coordinates of the faces.


    * **(****)** – Color.


    * **opacity** (*float*) – Opacity



#### add_line(start, end, color=(0.5, 0.5, 0.5), width=1)
Adds a line.


* **Parameters**


    * **start** – Starting coordinates for line.


    * **end** – Ending coordinates for line.


    * **color** – Color for text as RGB. Defaults to grey.


    * **width** – Width of line. Defaults to 1.



#### add_partial_sphere(coords, radius, color, start=0, end=360, opacity=1.0)
Adding a partial sphere (to display partial occupancies.


* **Parameters**


    * **coords** (*nd.array*) – Coordinates


    * **radius** (*float*) – Radius of sphere


    * **(****)** (*color*) – Color of sphere.


    * **start** (*float*) – Starting angle.


    * **end** (*float*) – Ending angle.


    * **opacity** (*float*) – Opacity.



#### add_picker()
Create a cell picker.


#### add_picker_fixed()
Create a cell picker.Returns:


#### add_polyhedron(neighbors, center, color, opacity=1.0, draw_edges=False, edges_color=(0.0, 0.0, 0.0), edges_linewidth=2)
Adds a polyhedron.


* **Parameters**


    * **neighbors** – Neighbors of the polyhedron (the vertices).


    * **center** – The atom in the center of the polyhedron.


    * **color** – Color for text as RGB.


    * **opacity** – Opacity of the polyhedron


    * **draw_edges** – If set to True, the a line will be drawn at each edge


    * **edges_color** – Color of the line for the edges


    * **edges_linewidth** – Width of the line drawn for the edges



#### add_site(site)
Add a site to the render window. The site is displayed as a sphere, the
color of which is determined based on the element. Partially occupied
sites are displayed as a single element color, though the site info
still shows the partial occupancy.


* **Parameters**

    **site** – Site to add.



#### add_text(coords, text, color=(0, 0, 0))
Add text at a coordinate.


* **Parameters**


    * **coords** – Coordinates to add text at.


    * **text** – Text to place.


    * **color** – Color for text as RGB. Defaults to black.



#### add_triangle(neighbors, color, center=None, opacity=0.4, draw_edges=False, edges_color=(0.0, 0.0, 0.0), edges_linewidth=2)
Adds a triangular surface between three atoms.


* **Parameters**


    * **neighbors** – Atoms between which a triangle will be drawn.


    * **color** – Color for triangle as RGB.


    * **center** – The “central atom” of the triangle


    * **opacity** – opacity of the triangle


    * **draw_edges** – If set to True, the a line will be  drawn at each edge


    * **edges_color** – Color of the line for the edges


    * **edges_linewidth** – Width of the line drawn for the edges



#### display_help()
Display the help for various keyboard shortcuts.


#### orthongonalize_structure()
Orthogonalize the structure.


#### redraw(reset_camera=False)
Redraw the render window.


* **Parameters**

    **reset_camera** – Set to True to reset the camera to a
    pre-determined default for each structure. Defaults to False.



#### rotate_view(axis_ind=0, angle=0)
Rotate the camera view.


* **Parameters**


    * **axis_ind** – Index of axis to rotate. Defaults to 0, i.e., a-axis.


    * **angle** – Angle to rotate by. Defaults to 0.



#### set_structure(structure: [Structure](pymatgen.core.structure.md#pymatgen.core.structure.Structure), reset_camera=True, to_unit_cell=True)
Add a structure to the visualizer.


* **Parameters**


    * **structure** – structure to visualize


    * **reset_camera** – Set to True to reset the camera to a default
    determined based on the structure.


    * **to_unit_cell** – Whether or not to fall back sites into the unit cell.



#### show()
Display the visualizer.


#### write_image(filename='image.png', magnification=1, image_format='png')
Save render window to an image.


* **Parameters**


    * **filename** – file to save to. Defaults to image.png.


    * **magnification** – Use it to render high res images.


    * **image_format** – choose between jpeg, png. Defaults to ‘png’.



#### zoom(factor)
Zoom the camera view by a factor.


### pymatgen.vis.structure_vtk.make_movie(structures, output_filename='movie.mp4', zoom=1.0, fps=20, bitrate='10000k', quality=1, \*\*kwargs)
Generate a movie from a sequence of structures using vtk and ffmpeg.


* **Parameters**


    * **structures** (*[*[*Structure*](pymatgen.core.structure.md#pymatgen.core.structure.Structure)*]*) – sequence of structures


    * **output_filename** (*str*) – filename for structure output. defaults to
    movie.mp4


    * **zoom** (*float*) – A zoom to be applied to the visualizer. Defaults to 1.0.


    * **fps** (*int*) – Frames per second for the movie. Defaults to 20.


    * **bitrate** (*str*) – Video bitate. Defaults to “10000k” (fairly high
    quality).


    * **quality** (*int*) – A quality scale. Defaults to 1.


    * **kwargs** – Any kwargs supported by StructureVis to modify the images
    generated.