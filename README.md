# Awesome Zarr with stars

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<img src="images/logo.png" alt="drawing" height="400"/>

[Zarr](https://zarr.dev/) is a cloud-native, chunked, compressed, and hierarchical array data format.

# Contents

[Resources](#resources)

* [Existing resources](#existing-resources)
* [Introductory videos](#introductory-videos)
* [Zarr V3](#zarr-v3)
* [Libraries](#libraries)
* [Platforms](#platforms)
* [Articles](#articles)
* [Talks & Videos](#talks--videos)
* [Life sciences](#life-sciences)

[Topics](#topics)

* [Zarr & other array data formats](#zarr--other-array-data-formats)
* [GeoZarr](#geozarr)
* [Zarr & STAC](#zarr--stac)

# Resources

## Existing resources

The [Zarr website](https://zarr.dev/) is already an excellent resource for learning about Zarr and its ecosystem.
This list is intended to complement the website with a curated and opinionated list of resources.

This list focuses on Geo/Earth Sciences, but is not limited to that domain.

### Existing lists

Lists

* [Zarr tutorials (zarr-developers/tutorials)](https://github.com/zarr-developers/tutorials) ⭐ 42 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2022-11-07
* [Projects using Zarr (zarr-developers/community#19)](https://github.com/zarr-developers/community/issues/19) ⭐ 18 | 🐛 45 | 📅 2023-11-29
* [Beautiful Zarr (zarr-developers/beautiful-zarr)](https://github.com/zarr-developers/beautiful-zarr) ⭐ 8 | 🐛 0 | 📅 2022-11-10
* The Zarr website already contains great lists:   [Zarr Implementations](https://zarr.dev/implementations/), [Zarr Datasets](https://zarr.dev/datasets/), [Zarr metadata conventions](https://zarr.dev/conventions/)
* See playlists & lists in [Talks & Videos](#talks--videos)

## Introductory videos

[Introductory talks Youtube playlist](https://www.youtube.com/playlist?list=PLvkeNUPrCU04Xvcph4ErxsRkZq28Oucr7)

Two excellent and up-to-date introductory talks:

* [Sanket Verma: The Beauty of Zarr](https://www.youtube.com/watch?v=OYaMi9WnQpA\&ab_channel=PyData)
* [Ryan Abernathey: State of Zarr](https://www.youtube.com/watch?v=1owtGSkNLQU\&ab_channel=Cloud-NativeGeospatialFoundation)

## Zarr V3

[Zarr V3](https://zarr-specs.readthedocs.io/en/latest/v3/core/v3.0.html) is the upcoming version of Zarr. It is a major update that will bring many new features and improvements.

If you're getting into Zarr now, it might be a good idea to start with Zarr V3.

* [Zarr-Python 3 and why you should be excited!](https://www.youtube.com/watch?v=g0nq4TtWuhM\&ab_channel=Pangeo)

For an excellent in-depth overview, see the [ESIP](https://www.esipfed.org/) series of talks

* [2023-03-27 ESIP Cloud Computing Cluster: Zarr - The Next Generation](https://www.youtube.com/watch?v=50_LwbIUXi0\&ab_channel=ESIP)
* [2023-04-24 ESIP Cloud Computing Cluster: Next Generation of Zarr Part 2/3 GeoZarr and Zarr Sharding](https://www.youtube.com/watch?v=a4-vmJRQcrg\&ab_channel=ESIP)
* [2023-05-22 ESIP CCC: Next Gen Zarr Part 3/3: accumulation proposal, Kerchunk and Pangeo-Forge](https://www.youtube.com/watch?v=ROsHdJI3-yw\&ab_channel=ESIP)

## Libraries

This list contains libraries that directly relate to Zarr in some way.

For implementations of Zarr, see [Zarr Implementations](https://zarr.dev/implementations/).

* [xpublish](https://github.com/xpublish-community/xpublish) ⭐ 209 | 🐛 28 | 🌐 Python | 📅 2026-08-17: Exposing as and consuming Zarr through a REST API
  * See also routers at [xpublish-community](https://github.com/xpublish-community), e.g. [xpublish-opendap](https://github.com/xpublish-community/xpublish-opendap) ⭐ 8 | 🐛 7 | 🌐 Jupyter Notebook | 📅 2026-08-17
  * [Improving Access to NOAA NOS Model Data with Kerchunk and Xpublish](https://www.youtube.com/watch?v=Bxkg6LJpKyc\&ab_channel=Pangeo)
* [ndpyramid](https://github.com/carbonplan/ndpyramid) ⭐ 120 | 🐛 15 | 🌐 Python | 📅 2026-07-06: utility for generating ND array pyramids using Xarray and Zarr
* [kerchunk](https://fsspec.github.io/kerchunk/), see [kerchunk section](#kerchunk)

Storage & I/O

* [KivkIO](https://github.com/rapidsai/kvikio/) ⭐ 276 | 🐛 79 | 🌐 C++ | 📅 2026-08-22: C++ and Python bindings to [cuFile](https://docs.nvidia.com/gpudirect-storage/api-reference-guide/index.html), enabling [GPUDirect Storage](https://developer.nvidia.com/blog/gpudirect-storage/)
* [rechunker](https://github.com/pangeo-data/rechunker) ⭐ 177 | 🐛 50 | 🌐 Jupyter Notebook | 📅 2026-08-17: disk-to-disk transformation for chunked arrays
* [Tensorstore](https://google.github.io/tensorstore/) and [xarray-tensorstore](https://github.com/google/xarray-tensorstore/) ⭐ 67 | 🐛 2 | 🌐 Python | 📅 2026-07-08: library for efficiently reading and writing large multi-dimensional arrays, has Zarr API
* [xpartition](https://github.com/spencerkclark/xpartition) ⭐ 31 | 🐛 4 | 🌐 Python | 📅 2026-07-31: writing large xarray datasets to Zarr. Works around shortcomings of Dask ([distributed#6360](https://github.com/dask/distributed/issues/6360) ⭐ 1,679 | 🐛 1,511 | 🌐 Python | 📅 2026-08-22)

ETL

* [Xarray](https://docs.xarray.dev/en/stable/index.html): Zarr is commonly written and accessed through xarray's API.
  * Xarray has its own [Zarr Encoding Specification](https://docs.xarray.dev/en/stable/internals/zarr-encoding-spec.html)
* [xarray-beam](https://github.com/google/xarray-beam/) ⭐ 170 | 🐛 22 | 🌐 Python | 📅 2026-08-06: Integration of [xarray](https://docs.xarray.dev/en/stable/index.html) and [Apache Beam](https://beam.apache.org/) built using Zarr.
* [Pangeo-forge](https://pangeo-forge.org/): Open-source data platform for transforming datasets into [analysis-ready cloud-optimized](https://ieeexplore.ieee.org/document/9354557) formats.
  * See [Pangeo Forge in 4 minutes](https://www.youtube.com/watch?v=qfAC-emFUxc\&ab_channel=CharlesStern) and [Pangeo Forge: Crowdsourcing Open Data in the Cloud- Ryan Abernathey | SciPy 2022](https://www.youtube.com/watch?v=sY20UpYCAEE\&ab_channel=Enthought)

Developer-oriented

* [numcodecs](https://github.com/zarr-developers/numcodecs) ⭐ 149 | 🐛 128 | 🌐 Python | 📅 2026-08-03: Compression and transformation codecs used by Zarr
* [pydantic-zarr](https://github.com/janelia-cellmap/pydantic-zarr) ⭐ 49 | 🐛 33 | 🌐 Python | 📅 2026-08-05: Pydantic models for Zarr objects
* [zarrdump](https://github.com/oliverwm1/zarrdump) ⭐ 34 | 🐛 3 | 🌐 Python | 📅 2026-02-15: Describe zarr stores from the command line
* [zarr\_checksum](https://github.com/dandi/zarr_checksum) ⭐ 13 | 🐛 13 | 🌐 Python | 📅 2026-02-02: Calculating checksum information form Zarr
* [traverzarr](https://github.com/xaviernogueira/traverzarr) ⭐ 2 | 🐛 2 | 🌐 Python | 📅 2024-02-08: Traversing Zarr JSON as if it's a filesystem

Visualization: For tools & libraries for visualization, see [visualization section](#visualization)

### Kerchunk

[Kerchunk](https://fsspec.github.io/kerchunk/) allows you to efficiently read chunked data formats such as GRID, NetCDF, COGs by exposing them as a Zarr store.

Talks and tutorials

* [All you need is Zarr](https://www.youtube.com/watch?v=0bqpxX3Nn_A)
* [2022 ESIP Kerchunk Tutorial](https://github.com/lsterzinger/2022-esip-kerchunk-tutorial) ⭐ 20 | 🐛 0 | 🌐 Jupyter Notebook | 📅 2024-02-29
* [Accessing NetCDF and GRIB file collections as cloud-native virtual datasets using Kerchunk](https://www.youtube.com/watch?v=cHYQuufXkP8\&ab_channel=Pangeo)

#### Future of Kerchunk

In the future, Kerchunk will be split into upstream functionality in Zarr itself and a new [VirtualiZarr](https://github.com/TomNicholas/VirtualiZarr) ⭐ 0 | 🐛 0 | 🌐 Python | 📅 2026-08-17 package.

* [Kerchunk JSON references](https://fsspec.github.io/kerchunk/spec.html) will become a part of the [Chunk manifest](https://github.com/zarr-developers/zarr-specs/issues/287) ⭐ 108 | 🐛 134 | 📅 2026-07-27
* For a full overview, see [Upstreaming Kerchunk](https://hackmd.io/t9Myqt0HR7O0nq6wiHWCDA?view)
* [What's Next for Kerchunk](https://www.youtube.com/watch?v=sYgZkqTAgYk\&ab_channel=Pangeo)

## Platforms

* [Arraylake](https://docs.earthmover.io/): a data lake platform based on Zarr. The company, [Earthmover](https://earthmover.io) was started by core Zarr developers.

## Articles

* [NASA IMPACT: Zarr Visualization Report](https://nasa-impact.github.io/zarr-visualization-report/)
* [Earthmover: cloud-native data loaders for machine learning using zarr and xarray](https://earthmover.io/blog/cloud-native-dataloader)
* [Zarr Sprint Recap](https://zarr.dev/blog/zarr-sprint-2024/) relevant overviews

## Talks & Videos

Existing lists

* [Zarr Developers playlists](https://www.youtube.com/@zarr_dev/playlists), namely
  * [Zarr: Introductory Talks](https://www.youtube.com/playlist?list=PLvkeNUPrCU04Xvcph4ErxsRkZq28Oucr7)
  * [Zarr: Zarr: Projects, Uses, Research and Workflows](https://www.youtube.com/playlist?list=PLvkeNUPrCU05qHkZso_T74yoayqLFHzkI)
* [Zarr Talks](https://zarr.dev/blog/zarr-talks/)
* [Introductory videos](#introductory-videos) in this list

Talks

* [Earthmover Webinar: Building a Planetary Scale Earth Observation Data Cube in Zarr ](https://vimeo.com/935616988/d9de7a97e9) with [code repository](https://github.com/earth-mover/serverless-datacube-demo) ⭐ 56 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2025-09-02 and [slides](https://app.hubspot.com/documents/22822350/view/788058450?accessId=9423df)
* [Earthmover Webinar: Analysis-ready Weather Forecast Data Cubes with Zarr
  ](https://www.youtube.com/watch?v=JwsrPVJPmag\&ab_channel=Earthmover) with [code repository](https://github.com/earth-mover/forecast-datacube-demo) ⭐ 25 | 🐛 1 | 🌐 Jupyter Notebook | 📅 2025-10-27 and [slides](https://app.hubspot.com/documents/22822350/view/814797193?accessId=e3acdd)
* Presentations for Sanket Verma's talks: [SciPy 2023](https://github.com/MSanKeys963/presentations/tree/main/scipy_2023) ⭐ 1 | 🐛 0 | 🌐 Jupyter Notebook | 📅 2026-06-25 and [PyCon DE 2023](https://github.com/MSanKeys963/presentations/tree/main/pycon_de_pydata_berlin_2023) ⭐ 1 | 🐛 0 | 🌐 Jupyter Notebook | 📅 2026-06-25
* [Presentation | Zarr: Community specification of large, cloud-optimised, N-dimensional, typed array storage](https://zenodo.org/records/8221177)

## Life sciences

Zarr has seen great adoption in the life sciences domain.

* [ome-zarr-py](https://github.com/ome/ome-zarr-py) ⭐ 258 | 🐛 80 | 🌐 Python | 📅 2026-08-18: Implementation of next-generation file format ([NGFF](https://ngff.openmicroscopy.org/)) specifications for storing bioimaging data in the cloud.
* [ez\_zarr](https://github.com/fmicompbio/ez_zarr) ⭐ 24 | 🐛 3 | 🌐 Python | 📅 2025-09-22: Easy, high-level access to OME-Zarr filesets
* [hdmf-zarr](https://github.com/hdmf-dev/hdmf-zarr) ⭐ 10 | 🐛 45 | 🌐 Python | 📅 2026-07-30: Zarr I/O backend for [HDMF](https://hdmf.readthedocs.io/en/stable/)
* [bdz](https://github.com/openssbd/bdz) ⭐ 7 | 🐛 2 | 🌐 Jupyter Notebook | 📅 2024-09-16: Zarr-based format for storing quantitative biosystems dynamics data

Talks and resources

* [Zarr | Life Science Lightning Talk | Trevor Manz | Dask Summit 2021](https://www.youtube.com/watch?v=8TlAAZcJnvA\&list=PLvkeNUPrCU04Xvcph4ErxsRkZq28Oucr7\&index=3\&ab_channel=Dask)
* [Accelerating Single-cell Bioinformatics with N-dimensional Arrays in the Cloud | ISMMS](https://www.youtube.com/watch?v=cYSYoiAVoEE)
* [What are next-generation file formats (NGFF)?](https://gerbi-gmb.de/2023/10/02/next-generation-file-formats-for-bioimaging/)

### Visualization

Zarr has seen most work on visualization in the bioimaging community:

* [Neuroglancer](https://github.com/google/neuroglancer) ⭐ 1,353 | 🐛 237 | 🌐 TypeScript | 📅 2026-08-14: WebGL-based viewer for volumetric data
* [Vizarr](https://github.com/hms-dbmi/vizarr) ⭐ 199 | 🐛 49 | 🌐 TypeScript | 📅 2026-06-22: interactive viewer built using [viv](https://github.com/hms-dbmi/viv) ⭐ 359 | 🐛 71 | 🌐 JavaScript | 📅 2026-08-10 (OME-Zarr and OME-TIFF)
* List: [Image viewers with OME-Zarr support](https://ngff.openmicroscopy.org/tools/)
* [WEBKNOSSOS](https://webknossos.org/): web-based visualization & annotation tool, supports OME-Zarr
* [Napari](https://napari.org/stable/):  interactive viewer
* [BigDataViewer](https://imagej.net/plugins/bdv/)

# Topics

## Zarr & other array data formats

For a general overview, see

* [Introduction to Cloud-Native Geospatial Formats](https://www.youtube.com/watch?v=zMPFHwW7Ujo\&ab_channel=Cloud-NativeGeospatialFoundation)
* [Cloud-Optimized Geospatial Formats Guide](https://guide.cloudnativegeo.org/).

Essentially all other common array data formats can be exposed as Zarr. See [Kerchunk](#kerchunk).

### NetCDF & HDF5

Zarr, NetCDF, and HDF5 are three separate data formats that nonetheless relate to each other in multiple ways.

* Zarr inherits its hierarchical structure from HDF5.
* Zarr is commonly accessed through [xarray](https://docs.xarray.dev/en/stable/index.html), whose [data models are based on the NetCDF data format](https://docs.xarray.dev/en/stable/getting-started-guide/why-xarray.html#core-data-structures)
* NetCDF4 can [use HDF5 as a backend](https://www.bic.mni.mcgill.ca/users/sean/Docs/netcdf/guide.txn_85.html)
* [NCZarr](https://docs.unidata.ucar.edu/nug/current/nczarr_head.html) is an extension of the Zarr format to map it to a subset of the NetCDF data model.

Resources

* [A Comparison of HDF5, Zarr, and netCDF4 in Performing Common I/O Operations](https://arxiv.org/abs/2207.09503)
  HDF5
* [Pangeo: HDF5 at the speed of Zarr](https://www.youtube.com/watch?v=iRboOFIB74o\&ab_channel=Pangeo)
* [Joe Jevnik: Zarr vs. HDF5 | PyData New York 2019](https://www.youtube.com/watch?v=-l445lCPTts\&ab_channel=PyData)

### COG: Cloud-Optimized GeoTIFF

* [Overview: Zarr - A Cloud Native ND Array Format @ 19:17](https://youtu.be/KiiKvXzhyMs?si=4sEqZ00lcl0WNXUb\&t=1157)
* [COG and Zarr for Geospatial Data](https://paper.dropbox.com/doc/COG-and-Zarr-for-Geospatial-Data--CNQFg0s2jhdrXjbNGDQ7Y~qgAg-UyeMJVOn5PqcNJoifLQiV)

### N5

Zarr and N5 are two similar array data formats that share common goals and development.

The Zarr V3 spec aims to provide a common implementation target (sources: [1](https://zarr.dev/zarr/specs/2019/06/19/zarr-v3-update.html), [2](https://zarr-specs.readthedocs.io/en/latest/v3/core/v3.0.html))

Links

* [n5](https://github.com/saalfeldlab/n5) ⭐ 204 | 🐛 29 | 🌐 Java | 📅 2026-08-19
* [z5](https://github.com/constantinpape/z5) ⭐ 133 | 🐛 25 | 🌐 C++ | 📅 2026-07-02: C++ and Python interface for datasets in zarr and n5 format
* [Zarr N5 spec diff (zarr-specs#3)](https://github.com/zarr-developers/zarr-specs/issues/3) ⭐ 108 | 🐛 134 | 📅 2026-07-27
* [zarr.n5](https://zarr.readthedocs.io/en/stable/api/n5.html)

## GeoZarr

GeoZarr is a proposal for a Zarr-based geospatial data format, being submitted as an [OGC standard](https://www.ogc.org/standards/)

GeoZarr will define a [metadata convention](https://zarr.dev/conventions/) for Zarr stores that contain geospatial data.

It will also define the relationship of Zarr with [CF](https://cfconventions.org/) and NetCDF

Links

* [Specs](https://github.com/zarr-developers/geozarr-spec) ⭐ 210 | 🐛 37 | 🌐 HTML | 📅 2026-08-03
* [Current status of GeoZarr](https://www.youtube.com/watch?v=arjEaBwXRxg\&ab_channel=Cloud-NativeGeospatialFoundation)

## Zarr & STAC

[STAC](https://stacspec.org/en/) provides a common structure for describing and cataloging spatiotemporal assets.

With its hierarchical structure and key-value metadata support, Zarr's capabilities overlap significantly with STAC.

The communities have not yet converged on a canonical representation of Zarr datasets through STAC.

Today, a good example of exposing Zarr in STAC is  Planetary Computer

* [xstac](https://github.com/stac-utils/xstac/tree/main?tab=readme-ov-file) ⭐ 73 | 🐛 4 | 🌐 Python | 📅 2025-02-25: STAC from xarray
* Related STAC extensions: [xarray-assets](https://github.com/stac-extensions/xarray-assets) ⚠️ Archived, [datacube](https://github.com/stac-extensions/datacube) ⭐ 25 | 🐛 7 | 📅 2026-06-18
* [Reading Zarr Data](https://planetarycomputer.microsoft.com/docs/quickstarts/reading-zarr-data/)
* STAC collection: [Daymet Annual North America](https://planetarycomputer.microsoft.com/dataset/daymet-annual-na)
* STAC collection: [CIL Global Downscaled Projections for Climate Impacts Research](https://planetarycomputer.microsoft.com/dataset/group/cil-gdpcir)

More discussion & Related links

* [stac-spec#781: Zarr Extension?](https://github.com/radiantearth/stac-spec/issues/781) ⭐ 919 | 🐛 48 | 🌐 JavaScript | 📅 2026-08-17
* [geozarr-spec#32: Integration of Zarr with STAC Catalogs](https://github.com/zarr-developers/geozarr-spec/issues/32) ⭐ 210 | 🐛 37 | 🌐 HTML | 📅 2026-08-03
* [Pangeo: Metadata duplication on STAC zarr collections](https://discourse.pangeo.io/t/metadata-duplication-on-stac-zarr-collections/3193/6)
* [Tom Augspurper: STAC and Kerchunk](https://tomaugspurger.net/posts/stac-updates/#stac-and-kerchunk)
* [Presentation | Daniel Jahn – STAC vs Zarr](https://cloud.mohr.ws/index.php/s/8oyTgc2kRK6QQcC?dir=undefined\&openfile=8487)
* [Arraylake](https://docs.earthmover.io/) a data lake platform that is arguably the first example of a pure Zarr data catalog

In the future, the [Zarr V3 Spec](#zarr-v3) and [GeoZarr convention](#geozarr) will likely enable greater interoperability between STAC and Zarr.

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-08-22._
