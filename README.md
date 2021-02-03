# voila-nbgallery

[![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

**Experimental work in progress - subject to change!**

This project contains [Voila](https://voila.readthedocs.io/en/stable/) templates to use in offline scenarios and/or in conjunction with [nbgallery](https://github.com/nbgallery/nbgallery).  These templates use jinja template inheritance to build on top of upstream templates maintained by the [Voila project](https://github.com/voila-dashboards).

## Templates in this package

 * **offline-lab** - Voila's default template, patched to work offline (nothing nbgallery-specific)
   * Patch for using [Qgrid](https://github.com/quantopian/qgrid) in conjunction with `enable_nbextensions=True` ([voila#72](https://github.com/voila-dashboards/voila/issues/72))
   * Local copy of font-awesome stylesheet ([voila#539](https://github.com/voila-dashboards/voila/issues/539))
 * **offline-gridstack** - [voila-gridstack](https://github.com/voila-dashboards/voila-gridstack) template, patched to work offline (nothing nbgallery-specific)
   * Qgrid and font-awesome patches as above
   * Local copy of gridstack javascript and stylesheet ([voila-gridstack#26](https://github.com/voila-dashboards/voila-gridstack/issues/26))
 * **nbgallery-material** - Prototype nbgallery template based on [voila-material](https://github.com/voila-dashboards/voila-material)
   * Qgrid and font-awesome patches as above
   * Workaround for javascript widget error ([voila-material#22](https://github.com/voila-dashboards/voila-material/issues/22))
   * Displays nbgallery metadata if present in the notebook
     * *Note: prototype only; nbgallery doesn't currently populate all the fields used by the template.*
   * Sets the nbgallery notebook and revision id as environment variables in the kernel - this can be used for provenance of external actions taken by the notebook
     * *Note: this only works if Voila is running as a server extention; in standalone mode, execute requests are blocked.*
     
See the [notebooks](https://github.com/nbgallery/voila-nbgallery/tree/main/notebooks) directory for some examples.
