+++
date = '2026-08-01T12:00:00-07:00'
draft = false
title = 'The Beginning of NoteNodes & P2KG'
+++

**My chat with ChatGPT 5.6:**

**Marina:**

I have an idea called NoteNodes: a user interface designed to improve human–AI collaboration. The core concept is to help users break complex tasks into clear, manageable steps. Users define essential milestones within the workflow, while the AI executes each step, reports progress, and pauses for review or approval at key checkpoints.

**ChatGPT 5.6:**

NoteNodes is a visual, milestone-driven workspace for collaborating with AI. Instead of giving an AI one large prompt and hoping for the right result, users break work into connected nodes, define essential checkpoints, and control how the AI executes the workflow.
...
....

**Marina:**

Okay, if I want to pursue this project, how could NoteNodes help?

I have an idea called P2KG—“from one paper to a knowledge graph.” When researchers discover an interesting paper, P2KG would use it as a seed to build a knowledge graph of related papers, concepts, authors, methods, and findings. This would help researchers better understand the paper’s context and explore the broader research landscape around it.

I’m considering building a user interface for the frontend. The backend would support discovering and retrieving papers from online sources, selecting relevant papers, extracting key information, and constructing an interactive knowledge graph. The ultimate goal is to help researchers understand a topic, identify important connections, and navigate the surrounding literature more efficiently.
What capabilities could NoteNodes provide to support this workflow?

**ChatGPT 5.6:**

## How NoteNodes should help you build P2KG

**P2KG:** Turn one seed paper into an interactive knowledge graph that helps researchers understand the paper, discover related work, and expand their research scope.

NoteNodes should guide you through **two connected workflows**:

1. **Product-development workflow** — helping you design and build P2KG.
2. **Research workflow inside P2KG** — what researchers experience when using the product.

***

# 1. NoteNodes workflow for building P2KG

```text
Define research problem
        ↓
Clarify the knowledge graph’s purpose
        ↓
[Milestone: Approve product scope]
        ↓
Design the paper-discovery pipeline
        ↓
Design the knowledge-graph schema
        ↓
[Milestone: Validate with real papers]
        ↓
Prototype the researcher experience
        ↓
Design the backend architecture
        ↓
[Milestone: Approve MVP]
        ↓
Implement and evaluate
```

## Node 1 — Define the research problem

NoteNodes asks you to clarify:

- Who is the primary user?
- What happens after they find an interesting paper?
- What questions should P2KG help answer?
- Why is an ordinary citation graph insufficient?
- What should the researcher understand after using P2KG?

A useful problem statement:

> Researchers often discover an interesting paper but lack an efficient way to understand its surrounding concepts, methods, datasets, evidence, influential predecessors, and related research directions.

**Output:** A short problem statement and target-user definition.

***

## Node 2 — Define the researcher’s desired outcome

The graph should not simply show more papers. It should help answer questions such as:

- What problem does the seed paper address?
- What are its key claims and contributions?
- Which methods, models, datasets, and metrics does it use?
- Which prior papers does it build upon?
- Which papers support, extend, compare with, or contradict it?
- What research communities surround it?
- What gaps or possible next directions exist?

**Output:** A ranked list of research questions P2KG must answer.

### Milestone 1 — Approve the product scope

You review and select the initial purpose:

- Understanding the seed paper
- Mapping related literature
- Discovering research gaps
- Tracking methods and datasets
- Or a defined combination of these

This milestone prevents the project from becoming a generic “visualize all citations” product.

***

## Node 3 — Define the graph schema

This is one of the most important NoteNodes-assisted decisions.

### Suggested entity types

- Paper
- Author
- Institution
- Research problem
- Concept
- Claim
- Method
- Model
- Dataset
- Metric
- Experiment
- Result
- Limitation
- Research direction

### Suggested relationships

- `PAPER CITES PAPER`
- `PAPER EXTENDS PAPER`
- `PAPER COMPARES_WITH PAPER`
- `PAPER CONTRADICTS PAPER`
- `PAPER USES METHOD`
- `PAPER USES DATASET`
- `PAPER EVALUATES_WITH METRIC`
- `PAPER MAKES CLAIM`
- `CLAIM SUPPORTED_BY RESULT`
- `METHOD ADDRESSES PROBLEM`
- `PAPER HAS_LIMITATION`
- `PAPER SUGGESTS DIRECTION`
- `AUTHOR WROTE PAPER`

Each relationship should preserve its **evidence**, such as a quoted passage, page number, section, citation, or source URL.

**Output:** A versioned knowledge-graph schema.

### Milestone 2 — Validate the schema

Test the schema manually against three different paper types—for example:

- An empirical paper
- A survey paper
- A theoretical or methods paper

The milestone is complete only if the schema captures meaningful information across all three.

***

## Node 4 — Design the paper acquisition pipeline

NoteNodes helps you design the process:

```text
Paper URL, title, DOI, or PDF
        ↓
Resolve paper identity and metadata
        ↓
Find legal full-text source
        ↓
Download HTML or PDF
        ↓
Parse text, sections, tables, and references
        ↓
Validate extraction quality
```

Important backend responsibilities:

- Resolve DOI, arXiv ID, title, and canonical paper identity
- Retrieve metadata and available full text
- Detect duplicate versions of the same paper
- Parse sections and bibliography
- Preserve page and section references
- Distinguish paper content from external metadata
- Record retrieval source and availability
- Handle papers without accessible full text

**Output:** A paper-ingestion API and a normalized paper representation.

***

## Node 5 — Design related-paper discovery

P2KG should not automatically add every related paper. It should generate candidates and help the researcher select useful ones.

### Candidate sources

- References cited by the seed paper
- Papers that cite the seed paper
- Semantically similar papers
- Papers using the same methods or datasets
- Papers addressing the same research problem
- Surveys and foundational work
- Contrasting or contradictory work
- Recent follow-up papers

### Candidate-ranking dimensions

- Relevance to the seed paper
- Citation relationship
- Semantic similarity
- Novelty
- Recency
- Authority or influence
- Method overlap
- Potential disagreement
- Coverage contribution

### Human milestone

Before expanding the graph, show candidate papers as cards:

```text
Paper title
Why it is relevant
Relationship to seed paper
Important concepts
Available evidence
Add / Ignore / Save for later
```

The researcher, rather than the AI alone, controls graph expansion.

***

## Node 6 — Design knowledge extraction

The backend processes each selected paper through a traceable extraction workflow:

```text
Parse paper
    ↓
Extract entities
    ↓
Extract claims and relationships
    ↓
Link entities to existing graph nodes
    ↓
Attach evidence and confidence
    ↓
Detect conflicts and duplicates
    ↓
[Human validation]
    ↓
Commit to graph
```

Every extracted fact should include:

- Source paper
- Supporting passage
- Section or page
- Extraction method
- Confidence score
- Validation status
- Model and prompt version

This is critical because researchers need to distinguish between:

- A statement directly made by a paper
- An interpretation generated by AI
- A relationship inferred from metadata
- A conclusion validated by the researcher

### Milestone 3 — Extraction-quality review

Use a small evaluation set and measure:

- Entity precision and recall
- Relationship accuracy
- Claim-evidence alignment
- Duplicate entity rate
- Unsupported statement rate
- Researcher correction effort

Do not move directly from “the graph looks plausible” to production.

***

# 2. The P2KG end-user workflow

When a researcher uses P2KG, NoteNodes' milestone philosophy should appear directly in the experience.

## Stage 1 — Add a seed paper

Supported inputs:

- PDF upload
- Paper URL
- DOI
- arXiv link
- Title search

P2KG identifies candidate matches and asks the researcher to confirm the correct paper.

## Stage 2 — Generate a paper map

Before creating the larger graph, P2KG produces a structured map of the seed paper:

- Research problem
- Main contributions
- Key claims
- Methods
- Datasets
- Experiments
- Results
- Limitations
- Important concepts
- Suggested research directions

### Researcher checkpoint

The researcher can:

- Correct extracted information
- Merge or separate concepts
- Mark essential contributions
- Remove unsupported claims
- Select areas to explore

## Stage 3 — Suggest graph-expansion directions

Instead of one generic “find related papers” action, offer research-oriented paths:

- **Foundations:** What work led to this paper?
- **Extensions:** What later work builds on it?
- **Alternatives:** What competing methods exist?
- **Evidence:** What supports or challenges its claims?
- **Applications:** Where has the method been used?
- **Datasets:** What other work uses the same data?
- **Research gaps:** Which limitations remain unresolved?

The user selects one or more directions.

## Stage 4 — Select candidate papers

P2KG retrieves and ranks candidates, but pauses before ingestion.

The researcher approves papers individually or in batches and can control:

- Maximum graph depth
- Maximum number of papers
- Publication range
- Topic boundaries
- Inclusion and exclusion criteria
- Desired expansion direction

## Stage 5 — Build and inspect the graph

The graph should have multiple complementary views:

### Paper view

Shows citation and semantic relationships between papers.

### Concept view

Shows methods, datasets, problems, claims, and results across papers.

### Research-path view

Shows an understandable narrative:

```text
Foundational problem
    → original method
    → seed paper’s improvement
    → later extensions
    → unresolved limitation
```

### Evidence view

Selecting an edge reveals exactly why the connection exists:

- Supporting text
- Paper and section
- Relationship type
- Confidence
- Whether the relationship is extracted, inferred, or human-confirmed

## Stage 6 — Research synthesis

P2KG should convert the graph into useful research outputs:

- Literature overview
- Comparison table
- Method evolution timeline
- Dataset and benchmark matrix
- Claim-evidence map
- Contradiction report
- Open-question list
- Reading plan
- Research brief with citations

***

# 3. Recommended P2KG UI

```text
┌─────────────────────────────────────────────────────────┐
│ Seed Paper | Search | Expand Graph | Export             │
├──────────────┬──────────────────────────┬───────────────┤
│ Research     │                          │ Selected Node │
│ scope        │     Knowledge Graph      │               │
│              │                          │ Summary       │
│ Foundations  │     Paper ─ Method       │ Evidence      │
│ Extensions   │       │       │          │ Relationships │
│ Alternatives │     Claim ─ Dataset      │ Confidence    │
│ Evidence     │                          │ Notes         │
│ Gaps         │                          │               │
├──────────────┴──────────────────────────┴───────────────┤
│ Suggested papers: Review 12 | Approved 5 | Rejected 3  │
└─────────────────────────────────────────────────────────┘
```

A node should open a detailed side panel rather than forcing users to understand everything visually. The graph is for exploration; the panel is for explanation and verification.

***

# 4. Practical MVP

The first version should follow one narrow but complete path:

```text
arXiv URL or PDF
    ↓
Extract seed-paper structure
    ↓
Retrieve references and semantically related papers
    ↓
Researcher selects 5–10 papers
    ↓
Extract concepts, methods, datasets, and claims
    ↓
Create an evidence-backed graph
    ↓
Generate a literature overview
```

## Build in the MVP

- PDF or arXiv ingestion
- Metadata and reference parsing
- Seed-paper structured summary
- Related-paper candidates
- Manual paper selection
- A limited graph schema
- Evidence attached to every extracted relationship
- Interactive graph and details panel
- Exportable literature overview

## Defer until later

- Fully autonomous graph expansion
- Support for every publisher
- Large-scale citation graphs
- Multi-agent orchestration
- Automatic contradiction detection across thousands of papers
- Complex collaborative editing
- Training a custom extraction model

***

# 5. Suggested system architecture

```text
Frontend
  ├── Seed-paper input
  ├── Paper review
  ├── Candidate selection
  ├── Graph exploration
  └── Evidence and synthesis panels

Backend API
  ├── Project and workflow service
  ├── Paper acquisition service
  ├── Parsing service
  ├── Discovery and ranking service
  ├── Knowledge extraction service
  ├── Entity-resolution service
  ├── Graph service
  └── Synthesis service

Storage
  ├── Object storage for papers
  ├── Relational DB for projects and jobs
  ├── Search/vector index for retrieval
  └── Graph DB or graph-oriented data layer

AI layer
  ├── Paper summarization
  ├── Structured extraction
  ├── Relationship classification
  ├── Candidate explanation
  └── Research synthesis
```

A dedicated graph database is not mandatory for the MVP. A relational database with typed node and edge tables can be simpler until graph traversal becomes a proven requirement.

***

# 6. Where NoteNodes provides the most value

For this project, NoteNodes should not merely act as a project checklist. It should enforce the important decisions:

| NoteNodes milestone   | Decision you must make                                |
| :-------------------- | :---------------------------------------------------- |
| Product scope         | What researcher problem does P2KG solve?              |
| Graph schema          | What information deserves to become a node or edge?   |
| Acquisition review    | Is the correct paper and full text available?         |
| Seed-paper review     | Is the AI’s understanding accurate?                   |
| Candidate selection   | Which papers should expand the graph?                 |
| Extraction validation | Are entities and relationships supported by evidence? |
| Synthesis review      | Does the output improve research understanding?       |
| MVP approval          | Is the workflow useful before increasing automation?  |

The central design principle for both products is:

> **AI proposes the structure and executes the expensive work; the researcher controls scope, validates evidence, and approves graph expansion.**
