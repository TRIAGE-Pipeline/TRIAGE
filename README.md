# *T*otal-evidence *R*outing and *I*ntegration *A*rchitecture for *G*rafting *E*volution (*TRIAGE*)

## TRIAGE Modules
TRIAGE is a modular, extensible framework designed to **route, integrate, and validate phylogenetic analyses across heterogeneous data types**. Each module performs a clearly defined task and can be executed independently or as part of a complete workflow.

### 1. Input & Data Harmonization Module
**Purpose:** 
Standardize and validate heterogeneous phylogenetic inputs prior to analysis.

**Functionality:**
- Accepts molecular, morphological, temporal, and geographic data
- Validates taxon names and identifiers across datasets
- Detects and reports missing taxa, incompatible partitions, and formatting issues
- Generates harmonized input files for downstream analyses

**Output:**
Cleaned, taxon-consistent datasets ready for phylogenetic inference.

### 2. Molecular Phylogenetic Analysis Module

**Purpose:**
Infer an initial molecular phylogeny using external phylogenetic software.

**Functionality:**
* Routes molecular data to supported inference programs (e.g., IQ-TREE, RAxML, MrBayes)
* Manages model selection, partition handling, and run configuration
* Captures inferred trees and associated support metrics

**Output:**
Molecular phylogeny with branch lengths and support values.

### 3. Morphological Phylogenetic Analysis Module

**Purpose:**
Infer a morphology-based phylogeny independently of molecular data.

**Functionality:**
* Routes morphological matrices to compatible inference programs
* Handles missing character data and taxon sampling differences
* Produces morphology-only trees suitable for downstream integration

**Output:**
Morphological phylogeny with associated support values.

### 4. Tree Routing & Constraint Module

**Purpose:**
Coordinate relationships between independently inferred trees.

**Functionality:**
* Identifies overlapping taxa between molecular and morphological trees
* Uses molecular trees as constraint topologies when appropriate
* Supports alternative routing strategies (e.g., unconstrained vs. constrained inference)
* Resolves taxon consistency issues analogously to absent-partition handling

**Output:**
Routed trees prepared for grafting or constrained inference.

### 5. Tree Grafting & Integration Module

**Purpose:**
Integrate molecular and morphological phylogenies into a unified evolutionary hypothesis.

**Functionality:**
* Grafts morphology-only clades onto molecular backbones using shared taxa
* Supports iterative grafting and re-evaluation
* Maintains provenance of each inferred relationship

**Output:**
Combined molecular–morphological phylogeny.

### 6. Support Synthesis Module

**Purpose:**
Quantify confidence by integrating support values across multiple analyses.

**Functionality:**
* Aggregates bootstrap, posterior probability, and alternative support metrics
* Supports combined or comparative support scoring
* Flags topological conflicts and low-confidence regions

**Output:**
Integrated tree annotated with synthesized support metrics.

### 7. Biogeographic Validation Module

**Purpose:**
Evaluate phylogenetic hypotheses using geographic and ecological context.

**Functionality:**
* Assigns taxa to predefined global ecoregions
* Tests tree plausibility using biogeographic coherence
* Identifies spatially inconsistent or improbable relationships
* Supports validation-informed re-routing or re-grafting

**Output:**
Biogeographically validated phylogeny and diagnostic reports.

### 8. Time Calibration Module

**Purpose:**
Estimate divergence times for integrated phylogenies.

**Functionality:**
* Supports literature-based node calibrations
* Supports tip-dating where applicable
* Interfaces with external dating software
* Produces time-scaled trees with uncertainty estimates

**Output:**
Time-calibrated phylogeny.

### 9. Workflow Orchestration Module

**Purpose:**
Coordinate execution of TRIAGE modules across multiple analytical pathways.

**Functionality:**
* Enables predefined or custom workflows
* Manages dependencies between modules
* Supports branching analytical pathways
* Logs all decisions and outputs for reproducibility

**Output:**
Reproducible, fully documented phylogenetic workflows.

### 10. Reporting & Export Module

**Purpose:**
Generate interpretable outputs for downstream use and publication.

**Functionality:**
* Exports trees in standard formats (Newick, Nexus, etc.)
* Produces summary reports of analyses and decisions
* Generates metadata for reproducibility and transparency

**Output:**
Publication-ready trees, reports, and metadata.