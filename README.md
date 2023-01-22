<div class="section" about="#" typeof="owl:Ontology">

  - Author  
    [<span property="foaf:name">Dorian
    Taylor</span>](https://doriantaylor.com/person/dorian-taylor#me)
  - Version  
    0.1
  - Created  
    December 4, 2022
  - Updated  
    January 21, 2023
  - Namespace URI  
    <https://vocab.methodandstructure.com/graph-tool#>
  - Preferred Namespace Prefix  
    `cgto`

The IBIS vocabulary is intended to only convey the essential semantic
and topological content of an IBIS network. There are nevertheless
additional constructs, that do not belong in the core vocabulary, that
need to be expressed in order to fully operationalize the information in
a piece of software. Such constructs include the users of the
environment, and the graphical representation of the network itself,
from colour palette to the relative (or absolute) geometry of the
individual nodes.

(We might actually want to consider calling this not “IBIS tool
ontology” and instead call it something like “collaborative graph
editor ontology”.)

so what ingredients do we need?

  - basic acl for users (view-only, comment, write; users themselves can
    be sioc that connects to foaf)

  - something that describes palettes for classes/properties/individuals
    (borrow selectors from shacl)
    
      - should be able to describe some kind of matrix for eg
        class/property along one side (eg hue) and ui state (sat, lum)
        on the other
      - should be able to delta the colour palette

  - some way to say how labels are constructed (can use loupe)

  - essential coordinate data for visual layouts (eg sugiyama
    rank/ordering)

  - consider different view states (eg clustering, edge contraction)

</div>

<div class="section">

## Classes

<div id="Space" class="section" about="cgto:Space" typeof="owl:Class">

### Space

An IBIS tool needs a shared logical space to lay out the argumentation
network.

  - Subclass of:  
    [sioc:Space](http://rdfs.org/sioc/ns#Space)

[Back to Top](https://vocab.methodandstructure.com/graph-tool#)

</div>

<div id="View" class="section" about="cgto:View" typeof="owl:Class">

### View

A partially or fully computed geometric view of a (sub)graph.

  - Subclass of:  
    [sioc:Space](http://rdfs.org/sioc/ns#Space)

[Back to Top](https://vocab.methodandstructure.com/graph-tool#)

</div>

</div>

<div class="section">

## Properties

</div>
