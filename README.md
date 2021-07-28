_Moved to https://github.com/GeoscienceAustralia/FSDF-KG_

# FSDF Knowledge Graph
This is the Knowledge Graph for the Foundational Spatial Data Framework (FSDF)'s Linked Data resources. 

FSDF is a Programme conducted by [ANZLIC](https://www.anzlic.gov.au/)/[ICSM](https://www.icsm.gov.au/) that aims to describe the provenance of a series of national spatial data products and ultimately secure their continued delivery. This repository holds a collection of models (ontologies), term lists (vocabularies or taxonomies) and data (datagraphs) that together form an [RDF](https://en.wikipedia.org/wiki/Resource_Description_Framework) _Knowledge Graph_, that can be used much like a database to answer queries about FSDF concerns.

For more information about FSDF, see <http://fsdf.org.au>. 


## Use

The individual elements within this Knowledge Graph (KG) - ontologies, taxonomies and datagraphs - can be loaded, viewed and used in any of many open and proprietary tools. General-purpose RDF tools such as Stnaford University's [Protégé](https://protege.stanford.edu/) can load all elements and show ontology and taxonomy structures. Triplestores (RDF databases) such as Apache's [Jena Fuseki](https://jena.apache.org/documentation/fuseki2/) can load the data and respond to standard "SPARQL" queries put to part or all of it.

The main tools used to create this KG were:

* [RDFlib](https://pypi.org/project/rdflib/) - an RDF manipulation library, written in Python
* [SURROUND Ontology Platform](https://surroundaustralia.com/sop) (SOP) - a customised implementation of [TopQuadrant's EDG](https://www.topquadrant.com/products/topbraid-enterprise-data-governance/) multi-graph management server
* [TopQuadrant's TopBraid Composer](https://www.topquadrant.com/products/topbraid-composer/) - an RDF integrated desktop environment (development studio)
* general-purpose text editors - in particular Microsoft's free [VS Code](https://code.visualstudio.com/)

RDFlib was used to create some of the RDF here, as well as to validate it and provide for some custom uses. SOP + TopBraid were the main systems used and all the resources in the `edg/` folder can be loaded into either SOP or TopBraid and used all together, and also used with other KGs.


## Provenance

This KG was built using non-RDF data sourced mainly from the [FSDF LINK](https://link.fsdf.org.au/) system which is a database of FSDF information made available as a Content Management System-managed website. 


## Related KGs & combined KG use

The project that built this KG - the [Location Index for Disaster Recovery](https://ldr.surroundaustralia.com/) project for [Geoscience Australia](https://www.ga.gov.au) - did so alongside  several other KGs:

* **ASGS KG**
    * a bundling of the [ASGS Ontology](https://linked.data.gov.au/def/asgs), [ASGS 2016 Dataset](https://linked.data.gov.au/dataset/asgs2016) and small, supporting RDF elements so make a KG containing everything needed to use ASGS data in RDF
* **Population KG**
    * a KG of [Australian Bureau of Statistics](https://www.abs.gov.au/) census data provided by new machine-data release intiatives at the ABS
    * this KG provides population _observations_, at points in time, of spatial elements within the ASGS KG's data
* **Loc-I KG**
    * a KG built from several, but not all, elements of the [Location Index](https://www.ga.gov.au/locationindex)'s public components
    * the Loc-I Ontology and some of the data graphs where includes but significantly altered for KG use
    * RDF elements not found in Loc-I were also added, such as the [Loc-I Data Profile](https://github.com/surroundaustralia/loci-data-profile), used for data validation
* **LDR KG**
    * a KG of FSDF datasets, interpreted into RDF from internal Geoscience Australia datasets

This KG and the three listed above can also be used in concert to answer questions spanning all their data. An example is:

* _What are the hydrological catchments in Queensland with the highest population growth?_

This sort of query requires data from the Population KG to be "reapportioned" to catchments in the Loc-I KG's Geofabric dataset via the ASGS' statistical areas.

# KG Elements
The machine-readable listing of this KG's elements can be found in its manifest, see `edg/manifest.ttl`. The main KG elements are:

* [FSDF Ontology](https://raw.githack.com/surroundaustralia/fsdf-kg/master/docs/fsdf.html)
    * this imports the [FSDF common elements ontology](https://raw.githack.com/GeoscienceAustralia/FSDF/master/common.html)
* multiple taxonomies
    * see `edg/taxonomies`
        * Ground Relations
        * Observable Properties
        * Operational Statuses
        * FSDF Themes
        * sub-themes of FDSF Themes
* several data graphs
    * Agencies
    * Datasets
    * Feature/Property Relations
    * Jurisdictions
    * Mandates

## License

The content in this repository has been created from Geoscience Australia source data, mainly from the FSDF LINK system but from other places too. Most of that information is licensed under the _Creative Commonns BY 4.0_ license and this content uses that same license. See the [license deed](LICENSE) for details.


## Contact Points

This dataset was built by [SURROUND Australia](https://surroundaustralia.com/) for [Geoscience Australia](https://www.ga.gov.au/).

For technical advice on this dataset and its use, contact the lead engineer responsible for building it:

**Nicholas Car**  
_Data Systems Architect_  
SURROUND Australia Pty Ltd  
<nicholas.car@surroundaustralia.com>  

For governance issues and extended use, contact the dataset's owner:

**Irina Bastrakova**  
_Director, Spatial Data Architecture_  
Geoscience Australia
<irina.bastrakova@ga.gov.au>  
