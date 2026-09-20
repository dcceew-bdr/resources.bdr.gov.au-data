# ASLS Vocabs

The 6 ASLS vocab here were originally list in the https://github.com/dcceew-bdr/bdr-reference-data-sync repo's config.tml file.

They were listed by w3id.org IRI but these have been replaced with linked.data.gov.au ones, as follows:

```
http://anzsoil.org/def/au/asls/land-surface ->  https://linked.data.gov.au/def/asls-land-surface
http://anzsoil.org/def/au/asls/landform ->      https://linked.data.gov.au/def/asls-landform
http://anzsoil.org/def/au/asls/location ->      https://linked.data.gov.au/def/asls-location
http://anzsoil.org/def/au/asls/soil-profile ->  https://linked.data.gov.au/def/asls-soil-profile
http://anzsoil.org/def/au/asls/substrate ->     https://linked.data.gov.au/def/asls-substrat
http://anzsoil.org/def/au/asls/vegetation ->    https://linked.data.gov.au/def/asls-vegetation
```

The 6 vocabs were downloaded from vocabs.ardc.gov.au on the 20th of September 2026, and as downloaded are stored in the 
files 

```
land-surface.ttl
landform.ttl
location.ttl
soil-profile.ttl
substract.ttl
vegetation.ttl
```

VoPub-valid copies of these vocabs are now loaded into the vocab register using these files in `resources/vocabs/items/asls`.

VocPub validity and other minor edits are noted in the loaded vocabs' `changeNote` properties.

## VocPub Validity

1. Replace IRIs as follows:

    http://anzsoil.org/def/au/asls/land-surface ->  https://linked.data.gov.au/def/asls-land-surface
    http://anzsoil.org/def/au/asls/landform ->      https://linked.data.gov.au/def/asls-landform
    http://anzsoil.org/def/au/asls/location ->      https://linked.data.gov.au/def/asls-location
    http://anzsoil.org/def/au/asls/soil-profile ->  https://linked.data.gov.au/def/asls-soil-profile
    http://anzsoil.org/def/au/asls/substrate ->     https://linked.data.gov.au/def/asls-substrat
    http://anzsoil.org/def/au/asls/vegetation ->    https://linked.data.gov.au/def/asls-vegetation

2. Add `owl:sameAs` for the new Concept Scheme IRI to the old one
3. Add in `skos:hasTopConcept` values for all `skos:topConceptOf` Concepts
4. Add `rdfs:isDefinedby` linking every Concept and Collection to the Concept Scheme
5. Remove all `dcterms:identifier` triples
6. Remove all `dcterms:title` triples where there is also a `skos:prefLabel` equivalent
7. Replace the following predicates:

    dcterms:contributor ->  schema:contributor
    dcterms:created ->      schema:dateCreated
    dcterms:creator ->      schema:creator
    dcterms:description ->  schema:description
    dcterms:isFormatOf ->   prof:wasDerivedFrom
    dcterms:license  ->     schema:license
    dcterms:modified ->     schema:dateModified
    dcterms:publisher ->    schema:publisher
    dcterms:rights ->       schema:copyrightNotice
    dcterms:source  ->      schema:citation

8. Replace the IRI <http://creativecommons.org/licences/by/4.0> with <http://purl.org/NET/rdflicense/cc-by4.0>
9. Replace the IRI <http://www.publish.csiro.au/> with <http://www.publish.csiro.au>