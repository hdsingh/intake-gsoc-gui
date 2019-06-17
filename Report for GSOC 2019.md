# Report for GSOC 2019

This page is the location for the reporting related to the GSoC 2019 project titled [A next-generation GUI for visualizing big gridded data in Python](https://github.com/ESIPFed/gsoc/issues/14).

Student: [Harman Deep Singh](https://github.com/hdsingh) Mentors: [Rich Signell](https://github.com/rsignell-usgs), [Martin Durant](https://github.com/martindurant) ESIP POC: [Annie Bryant Burgess](https://github.com/abburgess)

## Community Bonding Period (May 6th - May 26th):

[Community Bonding Period Milestone](https://github.com/intake/intake-gsoc-gui/milestone/1)

Activity:

1. Introduced myself and this project to the [ESIP](https://esip-all.slack.com/archives/C092JEU2C/p1557317043033200), [Intake](https://gitter.im/ContinuumIO/intake/archives/2019/05/18?at=5ce002d35b63ea22b3c8f337) and  [Pyviz](https://gitter.im/pyviz/pyviz/archives/2019/05/16?at=5cdcd628e7f42160fa982f7d) community.
2. Established [communication channel](https://gitter.im/ESIP_GUI/community) and had web meeting with mentors for discussion regarding workflow of the project.
3. Took overview of other catalog systems available. Watched [ESIP Tech Dive by Chris Holmes on STAC](https://www.youtube.com/watch?v=emXgkNutUTo).
4. Watched [ESIP Tech Dive talk on Intake](https://www.youtube.com/watch?v=PSD7r3JFml0).
5. Wrote the post [Beginning of my GSOC Journey!](https://hdsingh.github.io/pages/post1.html) ([Issue #4](https://github.com/intake/intake-gsoc-gui/issues/4)).
6. Set up development environment.
7. Tested use of catalogs with  [earlier dashboards](https://github.com/hdsingh/Dashboards) and discussed [Issue #3724 · pyviz/holoviews](https://github.com/pyviz/holoviews/issues/3724).
8. Read and executed the following documentations ([Issue #3](https://github.com/intake/intake-gsoc-gui/issues/3)):
    - [Xarray documentation](http://xarray.pydata.org/en/stable/)
    - [Intake documentation](https://intake.readthedocs.io/en/latest/)
    - [PyViz Tutorial — PyViz documentation](http://pyviz.org/tutorial/index.html)
    - [User Guide — HoloViews](http://holoviews.org/user_guide/index.html)
    - [Reference Guide — HoloViews](http://holoviews.org/reference/index.html)
    - [User Guide — GeoViews documentation](http://geoviews.org/user_guide/index.html)
    - [Gallery — GeoViews documentation](http://geoviews.org/gallery/index.html)
    - [User Guide — Panel documentation](https://pyviz-dev.github.io/panel/user_guide/index.html)
    - [Gallery — Panel](https://pyviz-dev.github.io/panel/gallery/index.html)
    - [User Guide — hvPlot](https://hvplot.pyviz.org/user_guide/index.html)

9. Explored Pangeo Datasets and Catalogs ([Issue #7](https://github.com/intake/intake-gsoc-gui/issues/7)).

10. I have also added `revising OOP Python concepts` to my studylist.

11. Prepared quick basic implementation of data description section ([Issue #5](https://github.com/intake/intake-gsoc-gui/issues/5#)).

Next week's Agenda:
- Discussion regarding design of [XrViz](https://github.com/intake/xrviz).
- Preparation of data input section.
- Learn using [Pytest](https://docs.pytest.org/en/latest/), which is going to be the testing framework for `XrViz`.

## Coding Period (May 27 - Aug 26)

### Week 1 (May 27 - June 2)

Weekly Activity

1. Took an overview of [Pytest](https://docs.pytest.org/en/latest/).
2. Understood working of `dfviz/widgets.py`.
3. Weekly e-meet: The following topics were discussed:
  - Tasks for Phase 1 (see [Phase I Milestone · GitHub](https://github.com/intake/intake-gsoc-gui/milestone/2)).
  - Tasks for week 1 in particular.
  - Working of  [Sigslot class](https://github.com/martindurant/dfviz/blob/master/dfviz/widget.py#L27).
4. Started implementation of Display and description section ([PR#2](https://github.com/intake/xrviz/pull/2)). Current status:

   1.Dimensions Display:
![Dimensions](assets/01_dimension.png)

   2.Coordinates Display:
![Coordinates](assets/02_coordinate.png)

   3.Variables Display:
![Variables](assets/03_variable.png)

   4.Attributes Display:
![Attributes](assets/04_attribute.png)

### Week 2 (June 03 - June 09)

Weekly Activity

1. Weekly e-meet: The following topics were discussed:
   - Appearance and functionality of display section. After discussion we concluded to have a simpler interface, displying only the `variables` in the selector. Other global properties would be always visible.
   - Overview and usage of tests.
   - Features and functionality of Fields panel.
2. Implemented simpler interface consisting of Display and description section ([PR #2](https://github.com/intake/xrviz/pull/2)). For more details please refer [Issue #14](https://github.com/intake/intake-gsoc-gui/issues/14) and [Issue #15](https://github.com/intake/intake-gsoc-gui/issues/14). Current status:

![Simpler Interface](assets/05_simpler_interface.png)
3. Started implementation of Basic Fields and Output Panel ([PR#3](https://github.com/intake/xrviz/pull/3)). Current status:

![Basic Fields and Output Panel](assets/06_fields_output.png)


### Week 3 (June 10 - June 16)

Weekly Activity

1. Improved the Basic fields and output panel. Added support for plotting data coordinates with respect to variables, which earlier resulted in errors.
2. Completed implementation of Basic Fields and Output Panel ([PR #3](https://github.com/intake/xrviz/pull/3)). The plotting function has been reimplemented using `sel` method.
3. The following topics were discussed in weekly e-meet:
   - `ignore_events` method present in `dfviz`, can be useful for some interactions in `xrviz`.
   - Demonstrated the working of interface.
   - `convert_widget` function.
   - Way to set/reset variables to coordinates.
   - Aggregation methods ([Issue #21](https://github.com/intake/intake-gsoc-gui/issues/21))
   - Overview of tasks for Phase 2:
       - Style Panel ([Issue #22](https://github.com/intake/intake-gsoc-gui/issues/22))
       - Projection Panel ([Issue #23](https://github.com/intake/intake-gsoc-gui/issues/23))
       - Time series extraction ([Issue #24](https://github.com/intake/intake-gsoc-gui/issues/24))
4. Started implementation of Aggregations in the fields panel ([PR #4](https://github.com/intake/xrviz/pull/4)). Current Status:
  - For single selection

![Aggregations 1 selection](assets/07_agg1.png)

  - For multiple selections
   
![Aggregations 1 selection](assets/08_agg2.png)
![Aggregations 1 selection](assets/09_agg3.png)

5. Started discussion to find out a possible solution to set and reset coordinates within the interface. For more details please refer [Issue #20](https://github.com/intake/intake-gsoc-gui/issues/20).
