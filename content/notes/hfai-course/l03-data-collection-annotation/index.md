+++
date = '2026-04-15T10:01:52-08:00'
draft = false
title = 'L3: Data Collection & Annotation'
+++

## Data-driven AI as a "Black Box"

- There is a low barrier to using AI because it is sufficient to provide input and output data to train a model.
- A major drawback is that users in non-computing domains often do not understand how a "black box" model works.
- Users also do not understand why the model works or why it fails.
- An AI system is only as good as its training data, often summarized as:
  > "Garbage in, garbage out."
- Getting the right data is a prerequisite for AI and Machine Learning (ML).

---

## Data Collection: Where and How

### Public Datasets
- Public datasets and repositories can be found on:
  - GitHub
  - Hugging Face
  - Kaggle
- Datasets can be downloaded directly or accessed via APIs.

### Web Scraping
- Web scraping involves programmatically navigating web pages and extracting information.
- Common tools include:
  - BeautifulSoup (Python)
- Scraping should be conducted responsibly and ethically:
  - Respect legal boundaries and Terms of Service.
  - Follow `robots.txt` directives.
  - Minimize impact on website resources.
  - Protect personal and sensitive information.
  - Comply with regulations such as GDPR.

### Generative AI and Artist Protection
- Scraping for generative AI training has led to protective tools such as **Glaze**.
- Glaze modifies artwork in ways that are imperceptible to humans but disrupt AI style imitation.

### Human Subjects Data Collection

#### Crowdsourcing
- Platforms such as Amazon Mechanical Turk allow large-scale data collection.
- A concern is that workers are often paid very little.

#### Lab Studies
- Useful when:
  - Studying users within larger systems.
  - Collecting sensor-based measurements.
  - Monitoring participant behavior in controlled environments.

#### Surveys
- Often embedded directly into applications.
- Quick and convenient for collecting user feedback.

---

## Construct, Proxy, and Label

### Definitions

| Term | Description |
|--------|-------------|
| Construct | The theoretical concept of interest that is often latent and unobservable. |
| Proxy | An observable measure used to represent the construct. |
| Label | The value actually recorded in the dataset. |

### Key Concepts

- **Construct Validity**
  - The extent to which a measurement accurately represents the theoretical construct it claims to measure.

- **Proxy Alignment**
  - The process of critically evaluating and justifying proxies used for unobservable constructs.

- **Goodhart's Law**
  > When a measure becomes a target, it ceases to be a good measure.

---

## Problems in Sampling

Data collection is fundamentally a sampling process. Because some data is selected while other data is excluded, inaccuracies, missing information, and biases are inevitable.

### Inaccurate Data
- Occurs when collected data is unrelated to the problem being studied.
- Leads models to learn spurious or misleading associations.

### Missing Data

#### Missing Cells
- Individual values are absent.
- Solutions:
  - Project data into a high-dimensional space.
  - Use unsupervised methods such as:
    - k-Nearest Neighbors (k-NN)

#### Missing Rows
- Entire observations are absent.
- Solutions:
  - Extrapolation
  - Interpolation
- Assumes temporal dependency among rows.

#### Missing Columns
- Entire features are absent.
- Solutions:
  - Autoencoders
  - Random Forest classifiers

### Data Imbalance
- Some classes contain significantly more samples than others.
- Example:
  - Geographic bias in medical AI where data comes primarily from a few states.

### Data Bias
- Existing societal biases become embedded in datasets.
- Common forms include:
  - Gender bias
  - Political bias
  - Age bias
  - Regional bias

---

## Ethical Issues & Best Practices

### Core Ethical Concerns
- Consent and awareness
- Privacy and sensitivity
- Exploitation and power imbalance

### Belmont Report (1979)

The Belmont Report provides foundational ethical principles for research involving human subjects.

#### Respect for Persons
- Clearly disclose data usage.
- Obtain meaningful consent.
- Allow participants to opt out.

#### Beneficence
- Minimize privacy risks.
- Consider downstream misuse.
- Avoid collecting unnecessary data.

#### Justice
- Reduce power asymmetries.
- Avoid overusing vulnerable populations.
- Ensure contributors also benefit from outcomes.

---

## Data Annotation: Alignment

Humans act according to mental models, making "ground truth" interpretive whenever tasks lack fully specified rules.

### Annotation Guidelines
- Instructions provided to annotators to ensure labels align with learning objectives.
- Help bridge domain knowledge gaps.

### Developing Annotation Guidelines
- Begin with expert-led calibration.
- Resolve disagreements early.
- Create representative examples linking data to labels.

### Annotation Consistency

#### Intra-Annotator Agreement
- Measures consistency of a single annotator across repeated labeling tasks.

#### Inter-Annotator Agreement
- Measures consistency across multiple annotators labeling the same data.

#### Cohen's Kappa
- Statistical measure of agreement between two annotators on categorical labels.

---

## Data Annotation: Bounded Resources and Adaptation

### Bounded Rationality
Human cognition is constrained by:
- Limited working memory
- Limited attention span
- Costs associated with perception and action

### Programmatic Annotation
Tools that assist or automate annotation include:
- Speed Labeling
- Snorkel

Benefits:
- Improve efficiency
- Reduce manual effort
- Scale annotation workflows

### Concept Drift
- Annotators may change their interpretation of labels over time.
- This occurs as they gain experience and encounter more examples.

### Structural Labeling
- Allows annotators to create subgroups within classes.
- Supports evolving understanding while maintaining consistency.

### Feedback-Guided Labeling
Interactive systems such as:
- Crayons
- EluciDebug

These systems integrate:
1. Data collection
2. Data annotation
3. Model training

into a continuous feedback loop.

---

## Philosophical Perspectives on Data Annotation

### Perspective 1: Discovery of Natural Laws
- Natural laws already exist.
- Human annotations help AI systems uncover these underlying patterns.

### Perspective 2: Programming Through Annotation
- Annotations directly shape model behavior.
- Human labelers effectively program the AI through the examples they provide.