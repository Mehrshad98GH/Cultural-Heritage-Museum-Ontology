Cultural Heritage / Museum Ontology
Overview
This project presents a Cultural Heritage / Museum Ontology designed to model the structure, holdings, and activities of a museum. It captures cultural objects, the collections and exhibitions they belong to, the people involved (artists, curators, visitors), and the events that affect objects over time (acquisition and restoration).

The ontology is developed in OWL 2.0 and implemented using Protégé, following standard ontology engineering practices. It corresponds to proposal #5 (Cultural Heritage / Museum Ontology) of the exam ontology list.

Objectives
Represent the core entities of a museum: institutions, buildings, galleries, collections, and cultural objects.
Distinguish artworks from historical artifacts, and the different roles people play (artist, curator, visitor).
Model the relationships between objects, collections, exhibitions, periods, and acquisition/restoration events.
Express part-of and associative relationships through object properties rather than the class hierarchy, keeping the taxonomy clean for automated reasoning.
Provide a well-documented, reasoner-consistent ontology suitable for academic evaluation.
Ontology Structure
Classes (15)
Museum
Building
Gallery
Collection
Cultural_Object
Artwork
Artifact
Exhibition
Person
Artist
Curator
Visitor
Acquisition
Restoration
Historical_Period
Only genuine is-a relationships are modelled with rdfs:subClassOf (Artwork/Artifact under Cultural_Object; Artist/Curator/Visitor under Person). The three person roles are declared mutually disjoint, as are Artwork and Artifact.

Object Properties (20)
has_Collection / belongs_To_Museum (inverse pair)
occupies_Building
has_Gallery / located_In_Building (inverse pair)
includes_Object / part_Of_Collection (inverse pair)
displays_Object / displayed_In_Exhibition (inverse pair)
held_In_Gallery
curated_By / curates_Exhibition (inverse pair)
created_Artwork / created_By (inverse pair)
from_Period
acquired_Through / acquisition_Of (inverse pair)
underwent_Restoration
restored_By
visits_Museum
Selected properties carry characteristics: belongs_To_Museum, located_In_Building, part_Of_Collection, and acquired_Through are functional. Every object property declares a domain and range.

Data Properties (20)
museum_Name, founding_Year
building_Name
gallery_Code
collection_Name
object_Title, inventory_Number, creation_Year, material_Type, dimensions
person_Name
birth_Year, death_Year, nationality
curator_Specialty
exhibition_Title, start_Date, end_Date
period_Label
acquisition_Date
Data properties declare domains and typed ranges (xsd:string, xsd:integer, xsd:date). museum_Name, inventory_Number, and person_Name are functional.

Annotation Properties
author
creation_Date
definition
example
Every class carries a definition annotation; representative classes also include an example.

Worked Example (Sample Individuals)
The ontology includes a small, consistent set of individuals to demonstrate the model:

National Art Museum — founded 1885, housed in Heritage Palace, which contains Gallery G1.
Renaissance Collection belongs to the museum and includes the artwork "Madonna of the Garden" (inventory INV-00123, 1505, oil on panel).
The artwork was created by Elena Visconti (Italian, 1470–1530), is from the Renaissance period, and was acquired through an acquisition dated 2019-06-15.
The "Renaissance Masters" exhibition (2026-03-01 to 2026-07-31) displays the artwork, is held in Gallery G1, and is curated by Marco Ricci (specialty: Renaissance Art).
Anna Bianchi is a visitor to the museum.
(All names are fictional and used only to illustrate the schema.)

Usage
Open CULTURAL HERITAGE MUSEUM ONTOLOGY.owl in Protégé.
Start a reasoner (e.g. HermiT or Pellet) via Reasoner → Start reasoner.
The ontology classifies consistently; you can inspect inferred types and explore the individuals in the Individuals tab.
File Format
The ontology is serialised in RDF/XML, the default OWL 2.0 format used by Protégé.

Author
Mehrshad Gharibi
