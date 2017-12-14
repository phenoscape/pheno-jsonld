pheno-jsonld
============

Currently just a summary of notes on interoperable format for expressing phenotypic data for taxa.

Most of the JSON-LD work at the workshop was to build direct mappings for the data model of NeXML
to JSON-LD.
We had some discussions of "warts" in NeXML that we might want to clean up.
These are mainly legacies of NEXUS.

## Unhelpful nesting
Note: here when we say a part of the NeXML spec is a list, we are speaking loosely; this
    is used to refer to elements that are repeatable at the same level in an XML doc.
These typs map naturally to a list of objects when the XML is translated to JSON.

  * `otu` is a list (repeatable element in XML) inside `otus`.
  * `tree` is  list inside `trees`

This is a legacy of `TAXA` and `TREES` blocks in NEXUS.
Note that each `otu` and each `tree` has a unique ID, the nesting of a taxon inside the container does not
    help a user find the fundamental elements.

Given that NeXML has a syntax for expressing a set of things
    (see https://github.com/nexml/nexml/wiki/NeXML-Manual#Sets_of_things_set ),
    there is no real need to treat the orginal "block" of TAXA or TREES as
    anything other than a set of `otu` or `tree` elements using the `set` syntax.

In JSON-LD, the nesting does not matter, given that docs can be framed in a wide variety of ways.

## Centrality of expressing character data in the context of matrices of homologous characters
A more generic framework for discussing phenotypic traits would be focused on the mapping of a
    organismal entity to a trait.
For example, in [TaxonWorks](http://taxonworks.org/) a user may want to discuss how an image
    relates to particular scorings of characteristics of an organism.
These could be forced into an `UNALIGNED` block in NEXUS, but is not an `unaligned` characters type
    in NeXML.

A more appealing layout would be a discription of possible character states for a trait (already
    present in the `state` construct of NeXML), a description of the state alphabet 
    of a homologous charactera (AKA "transformation series"; which are handled in the `char` 
    elements in NeXML [though `char` is  a horridly vague name]), and information about scorings
    of organismal entities.

## Not all scored entities are, even operationally, taxa
"OTU" is short for operational taxonomic unit.

# Links
This repo is product of the  Computable evolutionary phenotype knowledge workshop 
(see https://github.com/phenoscape/KB-DataFest-2017).


See also:
  * https://hackmd.io/CwdgZghhxgjAtMAxgIxIgHATgKzwziAAzwBsAJkQEwixICmRERSQA===?both
  * https://gitter.im/phenoscape-kb-datafest/nexml-to-json-ld

