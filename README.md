<div class="section" rel="foaf:primaryTopic" resource="#"
typeof="owl:Ontology">

Author  
<a href="https://doriantaylor.com/person/dorian-taylor#me"
rel="dct:creator" typeof="foaf:Person"><span property="foaf:name">Dorian
Taylor</span></a>

Version  
0.1

Created  
December 4, 2022

Updated  
January 21, 2023

December 12, 2023

Namespace URI  
<a href="https://vocab.methodandstructure.com/graph-tool#" about="#"
rel="sh:namespace vann:preferredNamespaceUri"><code>https://vocab.methodandstructure.com/graph-tool#</code></a>

Preferred Namespace Prefix  
`cgto`

Ontologies like [the IBIS
vocabulary](https://vocab.methodandstructure.com/ibis#) are intended to
only convey their essential semantic content. There are nevertheless
additional constructs, that do not belong in the core vocabulary, that
need to be expressed in order to fully operationalize the information it
describes as a piece of user-facing software. Such constructs include
the users of the environment, and the graphical representation of the
network itself, from colour palette to the relative (or absolute)
geometry of the individual nodes.

so what ingredients do we know we need?

-   basic ACL for users (e.g. view-only, comment, write; users
    themselves can be SIOC that connects to FOAF)

-   something that describes colour palettes for
    classes/properties/individuals (borrow selectors from SHACL)

    -   should be able to derive palettes from rules
    -   should be able to describe some kind of matrix for eg
        class/property along one side (eg hue) and ui state (eg sat,
        lum) on the other
    -   should be able to delta the colour palette for subclasses etc

-   some way to say how labels are constructed (can use loupe)

-   essential coordinate data for visual layouts (eg sugiyama
    rank/ordering)

-   consider different view states (eg clustering, edge contraction)

With respect to the graph itself, the goal of this vocabulary is to
provide just the information that only needs to be computed when the
graph's content is changed, so the computations can be cached and used
as inputs to more than one view.

</div>

<div class="section">

## Classes

![This diagram shows the classes and properties defined in this document
using solid lines, and third-party classes and properties using dashed
lines.](https://vocab.methodandstructure.com/graph-tool-classes)

<div id="Space" class="section" about="cgto:Space" typeof="owl:Class">

### `Space`

A graph tool needs a shared logical space to lay out its universe of
discourse.

Subclass of:  
<a href="http://rdfs.org/sioc/spec/#term_Space" rel="rdfs:subClassOf"
resource="sioc:Space"><code>sioc:Space</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="View" class="section" about="cgto:View" typeof="owl:Class">

### `View`

A partially or fully computed geometric rendering of a (sub)graph, or
the structured information needed to do so.

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Error" class="section" about="cgto:Error" typeof="owl:Class">

### `Error`

An error is a type of `cgto:View` the tool can send the user when
something is wrong. It is more suitable to send as a response *body*
than `http:Response`, which would be problematically self-referential.

Subclass of:  
<a href="https://vocab.methodandstructure.com/graph-tool#View"
rel="rdfs:subClassOf"><code>cgto:View</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Index" class="section" about="cgto:Index" typeof="owl:Class">

### `Index`

An index relates a `cgto:Space` to a set of `cgto:Inventory` resources,
via a set of `cgto:Summary` resources.

Subclass of:  
<a href="http://rdfs.org/sioc/spec/#term_Container"
rel="rdfs:subClassOf"
resource="sioc:Container"><code>sioc:Container</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Inventory" class="section" about="cgto:Inventory"
typeof="owl:Class">

### `Inventory`

An inventory is a de facto grouping of resources according to some
criterion.

Subclass of:  
<a href="http://rdfs.org/sioc/spec/#term_Container"
rel="rdfs:subClassOf"
resource="sioc:Container"><code>sioc:Container</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="Summary" class="section" about="cgto:Summary"
typeof="owl:Class">

### `Summary`

A summary indexes the available `cgto:Inventory` resources.

Subclass of:  
<a href="https://www.w3.org/TR/vocab-data-cube/#reference-datasets"
rel="rdfs:subClassOf" resource="qb:DataSet"><code>qb:DataSet</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

## Properties

![This diagram depicts the ontology from the point of view of its
properties.](https://vocab.methodandstructure.com/graph-tool-properties)

<div id="focus" class="section" about="cgto:focus"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### `focus`

The entity that takes primary focus in the space is what will be shown,
e.g. on the front page of a Web app.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#Space"
rel="rdfs:domain"><code>cgto:Space</code></a>

Sub-property of:  
<a href="http://rdfs.org/sioc/spec/#term_Space" rel="rdfs:subPropertyOf"
resource="http://rdfs.org/sioc/ns#space_of"><code>sioc:space_of</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="view" class="section" about="cgto:view"
typeof="owl:ObjectProperty">

### `view`

Relates the space to a view of said space.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#Space"
rel="rdfs:domain"><code>cgto:Space</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#View"
rel="rdfs:range"><code>cgto:View</code></a>

Sub-property of:  
<a href="http://rdfs.org/sioc/spec/#term_space_of"
rel="rdfs:subPropertyOf"
resource="http://rdfs.org/sioc/ns#space_of"><code>sioc:space_of</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/graph-tool#view-of"
rel="owl:inverseOf"><code>cgto:view-of</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="view-of" class="section" about="cgto:view-of"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### `view-of`

Relates a view back to its `cgto:Space`.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#View"
rel="rdfs:domain"><code>cgto:View</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Space"
rel="rdfs:range"><code>cgto:Space</code></a>

Sub-property of:  
<a href="http://rdfs.org/sioc/spec/#term_has_space"
rel="rdfs:subPropertyOf"
resource="http://rdfs.org/sioc/ns#has_space"><code>sioc:has_space</code></a>

Inverse of:  
<a href="https://vocab.methodandstructure.com/graph-tool#view"
rel="owl:inverseOf"><code>cgto:view</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="index" class="section" about="cgto:index"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### `index`

Connects the `cgto:Space` to its `cgto:Index` of resources.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#Space"
rel="rdfs:domain"><code>cgto:Space</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Index"
rel="rdfs:range"><code>cgto:Index</code></a>

Sub-property of:  
<a href="http://rdfs.org/sioc/spec/#term_space_of"
rel="rdfs:subPropertyOf"
resource="sioc:space_of"><code>sioc:space_of</code></a>

<a href="https://www.w3.org/1999/xhtml/vocab#index"
rel="rdfs:subPropertyOf" resource="xhv:index"><code>xhv:index</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="summary" class="section" about="cgto:summary"
typeof="owl:ObjectProperty">

### `summary`

Connects the `cgto:Space` to its `cgto:Index` of resources.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#Index"
rel="rdfs:domain"><code>cgto:Index</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Summary"
rel="rdfs:range"><code>cgto:Summary</code></a>

Sub-property of:  
<a href="http://rdfs.org/sioc/spec/#term_parent_of"
rel="rdfs:subPropertyOf"
resource="http://rdfs.org/sioc/ns#parent_of"><code>sioc:parent_of</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="by-class" class="section" about="cgto:by-class"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### `by-class`

Specifies the index of inventories organized by `rdfs:Class`.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#Index"
rel="rdfs:domain"><code>cgto:Index</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Summary"
rel="rdfs:range"><code>cgto:Summary</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/graph-tool#summary"
rel="rdfs:subPropertyOf"><code>cgto:summary</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="by-property" class="section" about="cgto:by-property"
typeof="owl:ObjectProperty owl:FunctionalProperty">

### `by-property`

Connects the `cgto:Space` to its `cgto:Index` of resources.

Domain:  
<a href="https://vocab.methodandstructure.com/graph-tool#Index"
rel="rdfs:domain"><code>cgto:Index</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Summary"
rel="rdfs:range"><code>cgto:Summary</code></a>

Sub-property of:  
<a href="https://vocab.methodandstructure.com/graph-tool#summary"
rel="rdfs:subPropertyOf"><code>cgto:summary</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

## Inventory Summaries

We use the <a href="https://www.w3.org/TR/vocab-data-cube/" about="#"
rel="owl:imports" resource="qb:">Data Cube Ontology</a> to summarize and
enumerate the resource inventories.

<div class="section">

### Data Structure Definitions

Data sets are described by data structure definitions which specify
different component properties.

<div id="resources-by-class" class="section"
about="cgto:resources-by-class" typeof="qb:DataStructureDefinition">

#### Resources by Class

This structure describes a data set that tabulates subject resources of
a certain `rdf:type`.

Components:  
<a href="https://vocab.methodandstructure.com/graph-tool#class"
rel="qb:dimension"><code>cgto:class</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#subjects"
rel="qb:attribute"><code>cgto:subjects</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#subject-count"
rel="qb:measure"><code>cgto:subject-count</code></a>

</div>

<div id="resources-by-property" class="section"
about="cgto:resources-by-property" typeof="qb:DataStructureDefinition">

#### Resources by Property

This structure describes a data set that tabulates both subject and
object resources by property (predicate).

Components:  
<a href="https://vocab.methodandstructure.com/graph-tool#property"
rel="qb:dimension"><code>cgto:property</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#subjects"
rel="qb:attribute"><code>cgto:subjects</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#subject-count"
rel="qb:measure"><code>cgto:subject-count</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#objects"
rel="qb:attribute"><code>cgto:objects</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#object-count"
rel="qb:measure"><code>cgto:object-count</code></a>

</div>

</div>

<div class="section">

### Dimension Properties

Dimension properties denote the axes along which the data set can be
partitioned.

<div id="class" class="section" about="cgto:class"
typeof="qb:DimensionProperty owl:ObjectProperty">

#### `class`

Specifies the `owl:Class` found in the `rdf:type` of the subjects.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="qb:Observation"><code>qb:Observation</code></a>

Range:  
<a href="https://www.w3.org/TR/rdf-schema/#ch_class" rel="rdfs:range"
resource="rdfs:Class"><code>rdfs:Class</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="property" class="section" about="cgto:property"
typeof="qb:DimensionProperty owl:ObjectProperty">

#### `property`

Specifies the property (predicate) in the statements from which subject
and object resources are enumerated.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="qb:Observation"><code>qb:Observation</code></a>

Range:  
<a href="https://www.w3.org/TR/rdf-schema/#ch_property" rel="rdfs:range"
resource="rdf:Property"><code>rdf:Property</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Measure Properties

Measure properties record the experimental data, which in this case
amounts to counts of resources.

<div id="subject-count" class="section" about="cgto:subject-count"
typeof="qb:MeasureProperty owl:DatatypeProperty">

#### `subject-count`

Specifies the number of subject resources in the selection criterion.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="qb:Observation"><code>qb:Observation</code></a>

Range:  
<a href="https://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="xsd:nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="object-count" class="section" about="cgto:object-count"
typeof="qb:MeasureProperty owl:DatatypeProperty">

#### `object-count`

Specifies the number of object resources in the selection criterion.

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="qb:Observation"><code>qb:Observation</code></a>

Range:  
<a href="https://www.w3.org/TR/xmlschema-2/#nonNegativeInteger"
rel="rdfs:range"
resource="xsd:nonNegativeInteger"><code>xsd:nonNegativeInteger</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

<div class="section">

### Attribute Properties

Attribute properties are used to qualify the data. In this case they are
being appropriated to link to the actual inventories of resources.

<div id="subjects" class="section" about="cgto:subjects"
typeof="qb:AttributeProperty owl:ObjectProperty">

#### `subjects`

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="qb:Observation"><code>qb:Observation</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Inventory"
rel="rdfs:range"><code>cgto:Inventory</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

<div id="objects" class="section" about="cgto:objects"
typeof="qb:AttributeProperty owl:ObjectProperty">

#### `objects`

Domain:  
<a href="https://www.w3.org/TR/vocab-data-cube/#ref_qb_Observation"
rel="rdfs:domain"
resource="qb:Observation"><code>qb:Observation</code></a>

Range:  
<a href="https://vocab.methodandstructure.com/graph-tool#Inventory"
rel="rdfs:range"><code>cgto:Inventory</code></a>

<a href="https://vocab.methodandstructure.com/graph-tool#"
rel="rdfs:isDefinedBy">Back to Top</a>

</div>

</div>

</div>
