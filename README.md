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


This repo is product of the  Computable evolutionary phenotype knowledge workshop 
(see https://github.com/phenoscape/KB-DataFest-2017).


See also:
  * https://hackmd.io/CwdgZghhxgjAtMAxgIxIgHATgKzwziAAzwBsAJkQEwixICmRERSQA===?both
  * https://gitter.im/phenoscape-kb-datafest/nexml-to-json-ld

