---
title: BioJava:CookBook3:ModFinder
---

How can I identify protein modifications in a structure?
--------------------------------------------------------

BioJava provide a module *biojava3-protmod* for identification of
protein pre-, co-, and post-translational modifications from structures.
[A list of protein
modifications](BioJava:CookBook3:SupportedProtMod "wikilink") has been
pre-loaded. It is possible to identify all pre-loaded modifications or
part of them.

Example: identify and print all preloaded modifications from a structure
------------------------------------------------------------------------

<java> void identifyAndPrintModfications(Structure struc) {

`   ProteinModificationIdentifier parser = new ProteinModificationIdentifier();`  
`   parser.identify(struc);`  
`   Set`<ModifiedCompound>` mcs = parser.getIdentifiedModifiedCompound();`  
`   for (ModifiedCompound mc : mcs) {`  
`       System.out.println(mc.toString());`  
`   }`

} </java>

Example: identify phosphorylation sites in a structure
------------------------------------------------------

<java> List<PDBResidueNumber> identifyPhosphosites(Structure struc) {

`   List`<PDBResidueNumber>` phosphosites = new ArrayList`<Integer>`();`  
`   ProteinModificationIdentifier parser = new ProteinModificationIdentifier();`  
`   parser.identify(struc, ProteinModification.getByKeyword("phosphoprotein"));`  
`   Set`<ModifiedCompound>` mcs = parser.getIdentifiedModifiedCompound();`  
`   for (ModifiedCompound mc : mcs) {`  
`       Set`<StructureGroup>` groups = mc.getGroups(ComponentType.AMINOACID);`  
`       for (StructureGroup group : groups) {`  
`           phosphosites.add(group.getPDBResidueNumber());`  
`       }`  
`   }`  
`   return phosphosites;`

} </java>