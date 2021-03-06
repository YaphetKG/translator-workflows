# Orange Team Workflow II TIDBIT
## Fanconi Anemia
### Background
Background Fanconi anemia is a rare genetic disease featuring characteristic developmental abnormalities, a progressive pancytopenia, genomic instability, and predisposition to cancer [1, 2]. The FA pathway contains a multiprotein core complex, including at least twelve proteins that are required for the monoubiquitylation of the FANCD2/FANCI protein complex and for other functions that are not well understood [3–6]. The core complex includes the Fanconi proteins FANCA, FANCB, FANCC, FANCE, FANCF, FANCG, FANCL, and FANCM. At least five additional proteins are associated with the FA core complex, including FAAP100, FAAP24, FAAP20, and the histone fold dimer MHF1/MHF2 [1, 4, 7–10]. The core complex proteins function together as an E3 ubiquitin ligase assembly to monoubiquitylate the heterodimeric FANCI/FANCD2 (ID) complex. The monoubiquitylation of FANCD2 is a surrogate marker for the function of the FA pathway [11]. USP1 and its binding partner UAF1 regulate the deubiquitination of FANCD2 [12]. The breast cancer susceptibility and Fanconi proteins FANCD1/BRCA2, the partner of BRCA2 (PALB2/FANCN), a helicase associated with BRCA1 (FANCJ/BACH1), and several newly identified components including FAN1, FANCO/RAD51C, and FANCP/SLX4 [13–17] participate in the pathway to respond to and repair DNA damage. (needs update with new refs)



### Candidate drug target discovery
An important area of focus in any rare disease research is the investigation of candidate drug targets. One means of identifying novel genes for further experimentation is through identifying candidate genes through analysis based on curated and structured data attributes. These attributes could be functions, phenotypes, interactions, co-expression results, etc. The distinction is that this is not primary data but data that has been published, then curated in structured databases as knowledge in a machine readable format. The inderect connections that come from this data modeling are what drive these types of analysis.

### The existing way
Traditionally, candidates are identied by querying pubmed, reading relevant literature, and leveraging domain expertise to identify and construct new ideas from the bits of knowledge extracted from the free text. Those ideas are then tested in the laboratory and iterated upon. On the other end of the spectrum, experimental high throughput methods generate lists of candidates that are so massive they are difficult to prioritize. There has to be a better way!

### The Translator way
The following is an example analysis that leverages curated knowledge (extracted and structured by professional curators with expertise in the domain) that has been semantically modeled to support machine readability in advanced querying and semantic similarity search algorithms. Essentially, genes are identified as similar based not only on the attributes that have been assigned to those genes (e.g. functions, phenotypes, etc) but also a higher level of understanding of how those attributes relate to one another. For example, while 'interstrand cross-link repair' and 'DNA repair' are not identical terms, 'interstrand cross-link repair' is a type of 'DNA repair'. The similarity algorithm takes the structure of the Gene Ontology (a structured vocabulary that describes functions and how they relate to each other) into consideration when calculating similarity.

#### Module1 Gene Based Analysis
We have developed workflow modules representing a collection of algorithms designed to start a set of genes associated with a disease and find candidate genes for further research based on a variety of similarity criteria.

The initial step in this analysis is to provide a disease of interest as the input. The entire system relies on stable identifiers from structured vocabularies such as the Monarch Disease Ontology (MONDO), rather than simply providing the text name of a disease.
