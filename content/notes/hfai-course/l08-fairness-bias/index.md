
+++
date = '2026-06-02T10:01:52-08:00'
draft = false
title = 'L8: Fairness & Bias'
+++

### Overview
This lecture explores fairness and bias in AI systems. It examines:

1. What fairness and bias mean.
2. Why fairness is a sociotechnical problem.
3. How bias enters AI systems throughout the data and modeling pipeline.
4. The harms caused by biased AI.
5. Human-centered approaches for mitigating bias.
6. User-driven debiasing of generative AI.

---

# 1. Introduction: Fairness & Bias in AI

## Motivating Example: Translation Bias

### Problem
Some languages (e.g., Turkish) use gender-neutral pronouns.

When translated into English:

- "doctor" may become "he"
- "nurse" may become "she"

### Why?

The model fills missing information using patterns learned from data.

### Key Insight

AI does not invent stereotypes.

It learns and reproduces stereotypes already present in society.

---

# 2. What Is Fairness?

## Definitions

### Merriam-Webster

> Fair or impartial treatment; lack of favoritism.

### Cambridge Dictionary

> Treating people equally or in a way that is right or reasonable.

### Course Perspective

> Fairness can be viewed as "reasonable (dis)favoritism."

---

## Why Fairness Is Difficult

The term "reasonable" introduces:

- Subjectivity
- Ambiguity
- Context dependence

Different people may disagree on:

- What is fair
- Who should benefit
- Which outcomes are equitable

### Main Takeaway

There is no single objective definition of fairness.

---

# 3. What Is Bias?

## Definition

Bias occurs when individuals, groups, or processes systematically treat people unfairly.

### Common Source

Stereotypes about:

- Ability
- Intelligence
- Personality
- Social roles

---

## Relationship Between Fairness and Bias

### Fairness

- Impartial treatment
- Equitable outcomes

### Bias

- Systematic favoritism
- Systematic disadvantage

Bias is often viewed as the opposite of fairness.

---

# 4. Fairness Is a Sociotechnical Problem

## Why It Is Not Purely Technical

Fairness depends on:

### Social Factors

- Culture
- History
- Values
- Power structures

### Technical Factors

- Data collection
- Labeling
- Modeling
- Evaluation

---

## Example: Content Moderation

Suppose an online forum is primarily used by:

- African American youth

Question:

Who should label inappropriate content?

Options:

- White upper-middle-class annotators?
- Community members?
- A mixture?

Each choice introduces different values and biases.

---

## Key Insight

There is no universally fair annotation strategy.

Fairness depends on perspective.

---

# 5. Bias Exists in Society Before AI

## Occupational Stereotypes

Examples:

- Nurses expected to be women
- Doctors expected to be men
- Carpenters expected to be men

---

## Racial Disparities

Examples:

- Differences in policing outcomes
- Differences in arrest rates
- Differences in use of force

---

## Key Point

AI systems often inherit existing societal inequalities.

AI is frequently a mirror of society.

---

# 6. How Technology Amplifies Existing Bias

## Example: Search Advertising

Research found:

- Searches for Black-sounding names were more likely to show arrest-record advertisements.

### Feedback Loop

Users click stereotype-consistent ads.

↓

Algorithms learn from clicks.

↓

Biased ads become more common.

↓

Bias becomes reinforced.

---

## Example: Search Autocomplete

Autocomplete systems learn from:

- User behavior
- Search histories

As a result:

- Existing stereotypes can become more visible.
- Harmful associations may be perpetuated.

---

# 7. Bias in Search and Recommendation Systems

## Image Search and Occupations

Research found:

### Male-Dominated Occupations

Search results showed:

- Even more men than exist in reality.

### Female-Dominated Occupations

Search results similarly exaggerated gender ratios.

---

## Why Does This Matter?

People exposed to biased search results:

- Perceive stereotypes as normal.
- Strengthen existing assumptions.

Even small changes in search results can affect social perception.

---

# 8. Why AI Models Become Biased

## Fundamental Reason: Induction

Machine learning performs induction:

### Process

Specific examples

↓

General patterns

↓

Predictions

---

## Problem

If training examples contain bias:

The model learns bias as if it were knowledge.

---

## Why Debiasing Is Hard

Requires:

- Diverse data
- Representative populations
- Reliable labels
- Clear ground truth

Even then:

- Fairness remains subjective.

---

# 9. Case Study: Image Generation Stereotypes

## Example

Prompt:

> "A photo of a software developer"

Generated images:

- 99% White

Real-world workforce:

- Approximately 56% White

---

## Another Example

Prompt:

> "Flight attendant"

Generated images:

- Nearly all female

Real-world workforce:

- Not 100% female

---

## Key Finding

Text-to-image models often amplify stereotypes rather than merely reflecting them.

---

# 10. Feedback Loops: AI Can Worsen Bias

## Housing Price Prediction Example

Suppose AI predicts:

- House value lower than actual value

Potential consequence:

- Buyers lose interest
- Demand decreases
- Price decreases further

---

## Self-Fulfilling Prophecy

Prediction

↓

Behavior change

↓

Outcome changes

↓

Prediction appears correct

---

## Main Takeaway

AI predictions can shape reality.

---

# 11. Harms Caused by Biased AI

## Allocative Harm

### Definition

Unfair distribution of resources or opportunities.

### Examples

- Hiring
- Loans
- Healthcare
- Criminal justice

Result:

Some groups receive fewer opportunities.

---

## Representational Harm

### Definition

Reinforcing harmful stereotypes.

### Examples

- "Doctor → male"
- "Nurse → female"

- Criminal stereotypes associated with race

Result:

Groups become socially marginalized.

---

# 12. Where Bias Enters the AI Pipeline

## Stage 1: Data Collection

### Example

Most medical AI systems were trained using data from:

- California
- Massachusetts
- New York

### Problem

Models may not generalize to:

- Other states
- Other countries
- Different populations

---

# Stage 2: Measurement Bias

## Example: Criminal Risk Prediction

Question:

How should "risk" be measured?

Possible proxies:

### Arrest Rate

Problem:

Arrests themselves may be biased.

### Court Appearance

Problem:

May depend on employment or transportation.

---

## Key Insight

The choice of measurement can introduce bias.

---

# Stage 3: Sensor Bias

## Example: Cameras

Historically:

- Film stocks optimized for lighter skin.
- Camera exposure systems trained on lighter-skinned subjects.

Result:

Poorer performance for darker skin tones.

---

## Lesson

Bias can originate before AI ever sees the data.

---

# Stage 4: Behavioral Data Bias

## Search Engines

A search engine may learn from:

- Which links users click

Question:

Why was the link clicked?

Because:

- It was relevant?
- Or because it appeared near the top?

---

## Confounding Variables

Observed behavior may not reflect true preference.

---

# Stage 5: Dataset Bias

## ImageNet Example

ImageNet categories originate from:

- WordNet
- Historical language resources

These sources may contain:

- Outdated terminology
- Historical assumptions
- Embedded biases

---

## Dataset Identification Study

Researchers trained a classifier to identify which dataset an image came from.

Result:

Performance far exceeded chance.

### Implication

Datasets have unique signatures and built-in biases.

---

# 13. Types of Dataset Bias

## 1. Selection Bias

Certain image types are overrepresented.

Examples:

- Nature scenes
- Street scenes
- Internet images

---

## 2. Capture Bias

Objects are photographed similarly.

Examples:

- Objects centered
- Similar camera angles

---

## 3. Label Bias

Annotators disagree.

Examples:

- Grass vs lawn
- Road vs street

---

## 4. Negative Set Bias

The dataset's definition of:

> "everything else"

is often incomplete.

Result:

Overconfident classifiers.

---

# 14. Correlation vs Causation

## Problem

AI learns correlations.

Examples:

### Knowledge

Smoking → cancer

### Potential Bias

Girls → pink

Boys → blue

---

## Why AI Struggles

The model sees patterns.

It cannot automatically determine:

- Which patterns are causal
- Which patterns are social stereotypes

---

## Main Takeaway

AI learns correlation, not causation.

---

# 15. Removing Sensitive Attributes Isn't Enough

## Common Idea

Remove:

- Gender
- Race
- Age

from training data.

---

## Problem: Proxy Variables

Other features may reveal the same information.

Example:

- Age when someone started programming
- Educational background
- Zip code

These may correlate with protected attributes.

---

## Key Insight

Bias can persist even after sensitive attributes are removed.

---

# 16. Biased Evaluation Metrics

## Example

Medical AI:

Overall error rate = 5%

Looks good.

---

### Subgroup Analysis

Population:

- A = 40%
- B = 40%
- C = 10%
- D = 5%
- E = 5%

Same number of errors per subgroup.

Result:

- A/B: 2.5% error
- C/D: 10% error
- E: 20% error

---

## Lesson

Aggregate metrics can hide subgroup disparities.

Always evaluate performance by subgroup.

---

# 17. Fairness Tradeoffs

## Example

Hiring Model

Uses:

- GPA
- Interview score

Question:

Should all groups use the same threshold?

Or:

Should different groups use different thresholds?

---

## Important Observation

Many disparities originate from society.

Changing thresholds alone may not solve underlying inequality.

---

# 18. User-Driven Debiasing of Generative AI

## Problem

Prompt:

> "A successful tech company CEO"

Generated images:

- Predominantly male

Reason:

CEO and male become entangled during training.

---

# Existing Approach

## Algorithm-Driven Debiasing

Researchers modify:

- Training procedures
- Latent spaces
- Model objectives

---

## Limitations

### 1. No Universal Definition of Bias

People disagree on fairness.

---

### 2. Perfect Debiasing Is Impossible

Bias may remain after deployment.

---

# HCI Perspective

## Give Users Control

Instead of relying solely on algorithms:

Allow users to:

- Detect bias
- Adjust outputs
- Correct stereotypes

---

# User-Driven Global Disentanglement

## Approach

Users provide:

### Positive Examples

Attributes to keep.

### Negative Examples

Attributes to remove.

---

## System Computes

A weighted combination of editing directions.

Result:

Users can reshape generated outputs.

---

# User-Driven Local Disentanglement

## Approach

Users select image regions.

Examples:

- Preserve glasses
- Remove beard

---

## Mechanism

Relevant GAN filters are:

- Strengthened
- Weakened

based on user preference.

---

# Results

User-driven approaches achieved:

- Comparable performance
- Sometimes better performance

than algorithm-only debiasing methods.

---

# Final Takeaways

## 1. Fairness Is Sociotechnical

Fairness depends on:

- Social values
- Human judgment
- Technical decisions

---

## 2. Bias Exists Before AI

AI often inherits:

- Historical inequalities
- Human stereotypes
- Structural disparities

---

## 3. Bias Appears Throughout the Pipeline

Sources include:

- Data collection
- Measurement
- Sensors
- Labels
- Datasets
- Evaluation metrics

---

## 4. AI Amplifies Existing Biases

Models frequently:

- Generalize bias
- Reinforce stereotypes
- Create feedback loops

---

## 5. Fairness Has No Single Definition

Different stakeholders may disagree about:

- What fairness means
- How it should be measured

---

## 6. Technical Fixes Alone Are Insufficient

Debiasing algorithms help, but cannot fully solve fairness problems.

---

## 7. Human-Centered AI Matters

Users should have:

- Awareness of bias
- Transparency
- Control mechanisms

to identify and correct unfair AI behavior.

---

# Key Design Philosophy

> Fairness is not purely an AI problem. It is a human and societal problem that becomes embedded in data, models, interfaces, and decisions. Building fair AI requires both technical solutions and human-centered design that gives users awareness, agency, and control.