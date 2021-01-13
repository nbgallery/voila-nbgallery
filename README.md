# voila-offline

**Experimental work in progress - subject to change!**

This project contains [Voila](https://voila.readthedocs.io/en/stable/) templates that have been patched to work better offline -- for example, on a corporate network that is isolated from the Internet by a firewall.  The patches use jinja template inheritance to add local copies of CSS and Javascript files referenced by the normal templates.  We currently have an offline version of the default Lab template and the [Gridstack](https://github.com/voila-dashboards/voila-gridstack) template.

## Testing

First, install voila-offline and start Voila:

```
# Install voila-offline
pip install .

# For the qgrid test notebook
pip install qgrid pandas
jupyter nbextension enable --py --sys-prefix qgrid

# Voila should serve nbextensions instead of relying on CDN
voila --port 8888 --VoilaConfiguration.enable_nbextensions=True ./notebooks
```

Next, **turn off your internet**, then compare the following URLs:

```
# Qgrid widget will not appear with default template
http://localhost:8888/voila/render/qgrid.ipynb
http://localhost:8888/voila/render/qgrid.ipynb?voila-template=offline-lab

# Font-awesome button icons will not appear with default template
http://localhost:8888/voila/render/font-awesome.ipynb
http://localhost:8888/voila/render/font-awesome.ipynb?voila-template=offline-lab

# Gridstack template will not display the grid properly
http://localhost:8888/voila/render/gridstack.ipynb?voila-template=gridstack
http://localhost:8888/voila/render/gridstack.ipynb?voila-template=offline-gridstack

# All three in one
http://localhost:8888/voila/render/gridstack-plus.ipynb?voila-template=gridstack
http://localhost:8888/voila/render/gridstack-plus.ipynb?voila-template=offline-gridstack
```
