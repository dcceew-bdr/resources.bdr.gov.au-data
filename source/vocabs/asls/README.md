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

Use the CodeX skill VocPub Validity to achieve basic validity: https://linked.data.gov.au/def/vocpub/skill-codex

Then:

1. Replace IRIs as follows:

    http://anzsoil.org/def/au/asls/land-surface ->  https://linked.data.gov.au/def/asls-land-surface
    http://anzsoil.org/def/au/asls/landform ->      https://linked.data.gov.au/def/asls-landform
    http://anzsoil.org/def/au/asls/location ->      https://linked.data.gov.au/def/asls-location
    http://anzsoil.org/def/au/asls/soil-profile ->  https://linked.data.gov.au/def/asls-soil-profile
    http://anzsoil.org/def/au/asls/substrate ->     https://linked.data.gov.au/def/asls-substrate
    http://anzsoil.org/def/au/asls/vegetation ->    https://linked.data.gov.au/def/asls-vegetation

2. Add `owl:sameAs` for the new Concept Scheme IRI to the old one
3. Remove all `dcterms:identifier` triples
4. Remove all `dcterms:title` triples where there is also a `skos:prefLabel` equivalent
5. Replace the IRI <http://www.publish.csiro.au/> with <http://www.publish.csiro.au>
6. `dcterms:Agent` -> `schema:Person` or `schema:Organization` 
7. For Agents: `foaf:name` -> `schema:name`
8. For Agents: add blank `schema:email` just to make for clean VocPub validation - later removed
9. For Concepts in one vocab in this set of 6 defined in another, remove the Concept re-definition but retain all Collection and other references to those Concepts 
10. To each vocab, add the following PREFIX declarations:

PREFIX : {CONCEPT-SCHEME-IRI + '/'}
PREFIX cs: {CONCEPT-SCHEME-IRI}

11. For all Concepts and Collections that do not have definitions but do have prefLabels, clone the `skos:prefLabel` values into `skos:definition`
12. For all `skos:prefLabel` and `skos:definition` values that do not indicate language, add it with `@en`
13. Move definition for these agents to the shared Agent resources (_background/agents.ttl):

```
<https://orcid.org/0000-0002-0693-1899>
    a schema:Person ;
    schema:email ""^^xsd:anyURI ;
    schema:name "Linda Gregory" ;
.

<https://orcid.org/0000-0002-3884-3420>
    a schema:Person ;
    schema:email "simon.cox@csiro.au"^^xsd:anyURI ;
    schema:name "Simon J D Cox" ;
.
```


For `location.ttl`:

x1. updated local definitions of ASGS States & Territories to IRIs from the ASGS dataset:

Using `PREFIX : <https://linked.data.gov.au/def/asls-location/>`:

 :state-or-territory-1 -> <https://linked.data.gov.au/dataset/asgsed3/STE/1>
 :state-or-territory-2 -> <https://linked.data.gov.au/dataset/asgsed3/STE/2>
 :state-or-territory-3 -> <https://linked.data.gov.au/dataset/asgsed3/STE/3>
 :state-or-territory-4 -> <https://linked.data.gov.au/dataset/asgsed3/STE/4>
 :state-or-territory-5 -> <https://linked.data.gov.au/dataset/asgsed3/STE/5>
 :state-or-territory-6 -> <https://linked.data.gov.au/dataset/asgsed3/STE/6>
 :state-or-territory-7 -> <https://linked.data.gov.au/dataset/asgsed3/STE/7>
 :state-or-territory-8 -> <https://linked.data.gov.au/dataset/asgsed3/STE/8>

x2. Removed the location definitions of `:state-or-territory-1` to `:state-or-territory-8` :
