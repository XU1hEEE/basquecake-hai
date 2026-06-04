
+++
date = '2026-05-18T10:01:52-08:00'
draft = false
title = 'L5: Model Interpretability'
+++

# Human Factors in Artificial Intelligence: 
## Why Do Humans Need to Understand AI?

As AI systems become more complex, users need ways to understand:

- Why a model made a prediction.
- How a model reaches a decision.
- Whether a model can be trusted.
- When a model may be wrong.

Model interpretability aims to bridge the gap between AI behavior and human understanding.

---

# Intrinsically Explainable Models

## Explainable BDI Agents

### Explaining Actions

Consider explaining why **Action b** is chosen.

### Relation II = All
If all requirements are needed:

- Use **Goal B**.
- Explanation:
  > Action b is taken because it is required to achieve Goal B.

### Relation II = One
If only one condition is needed:

- Use the enabling condition (e.g., **Belief 4**).
- Explanation:
  > Action b is taken (instead of a or c) because only Belief 4 is true.

### Relation II = Sequence
If actions occur sequentially:

- Use the subsequent action (e.g., **Action c**).
- Explanation:
  > Action b is taken because it enables the next action, c.

---

## Case-Based Reasoning (CBR)

### Core Idea

Case-Based Reasoning uses past experiences to solve and explain new problems.

Common examples include:

- Lawyers citing legal precedents.
- Labor mediators referencing previous agreements.
- Doctors diagnosing patients based on similar cases.

### Why It Is Explainable

If a previous case already has an explanation:

- The explanation can be reused.
- The new decision can be justified through similarity to past cases.

---

## Four Challenges of Case-Based Reasoning

### 1. Indexing
Finding the most similar previous case.

### 2. Interpretation
Determining what can be learned from the past case.

Possible outcomes:

- The previous solution applies.
- The previous solution demonstrates what will not work.

### 3. Adaptation
Modifying an old solution to fit a new situation.

Example:

- Updating a diagnosis when new symptoms appear.

### 4. Evaluation & Repair
Assessing whether the reused solution was successful.

---

## Linear Models as Explainable Models

A linear model combines features using weighted contributions.

Advantages:

- Individual feature contributions are visible.
- Users can inspect how each feature affects the output.

### Tornado Plots

Tornado plots visualize:

- Positive feature contributions.
- Negative feature contributions.
- Relative importance of each feature.

---

# Explainable Features

## What Makes Features Interpretable?

Interpretability depends heavily on feature design.

Two important factors:

1. Level of abstraction.
2. Number of features.

---

## Level of Abstraction

Consider a self-driving car stopping at a stop sign.

### Explanation A
> A region of the camera image matches a stop-sign template.

### Explanation B
> An octagonal shape is detected, the color histogram indicates red, and OCR identifies the word "STOP."

### Explanation C
> A neuron in the penultimate layer outputs 0.89.

Most users find Explanation B easiest to understand.

### Key Principle

Different users require different abstraction levels.

Examples:

| User | Preferred Explanation |
|--------|----------------------|
| Driver | Stop sign detected |
| Engineer | Shape, color, OCR evidence |
| ML Researcher | Neuron activations |

---

## Number of Features

Interpretability generally improves when:

- Fewer features are used.
- Important features are clearly identified.

### Example

Medical scoring systems often rely on:

- Symptoms
- Demographics
- A small set of measurements

Doctors can quickly compute and interpret results.

---

# What Makes a Model Interpretable?

Models tend to be interpretable when they are based on:

### Sequential Steps
- Users can ask:
  - Why?
  - How?

### Trees or Rules
- Decision trees
- Rule-based systems

### Linear Feature Combinations
- Explicit feature contributions

### Human-Understandable Features
Features should:

- Have meaningful abstraction levels.
- Be limited in number.

---

# Three Levels of Transparency

## 1. Simulatability

A human can manually simulate the model.

Example:

- Predicting the same output as the model using its parameters.

---

## 2. Decomposability

Individual components are understandable.

Examples:

- Features
- Rules
- Model modules

Each component can be explained independently.

---

## 3. Algorithmic Transparency

The learning process itself is understandable.

Example:

- Understanding how a linear regression line is fitted by minimizing error.

---

# Post-Hoc Explanation Methods

Sometimes the original model is not interpretable.

Instead, explanations are constructed after training.

---

# Reconstruction

## Core Idea

A model's internal reasoning may be difficult to understand.

Instead of exposing the actual reasoning process:

- Build a more understandable explanation.
- Create a "line of explanation."

---

## Line of Reasoning vs. Line of Explanation

Humans often explain decisions differently from how they actually reason.

### Example

Mathematical Statement

\[
\frac{b+\Delta}{a+\Delta} > \frac{b}{a}
\]

A mathematical proof may be difficult.

A child-friendly explanation:

> Adding more sugar to water makes it sweeter.

The explanation is:

- Easier to understand.
- Less complete.
- More relatable.

---

## Reconstructing Explanations

Goal:

Given:

\[
(x_1,x_2,\ldots,x_n)
\rightarrow y
\]

Create an interpretable representation showing:

- Which inputs mattered.
- Why the output occurred.

---

## Why Reconstruction Works

Human decision-making and human explanation are often different processes.

Benefits:

- Preserve predictive performance.
- Improve human understanding.

---

## Local Reconstruction: LIME

LIME explains a specific prediction by:

- Sampling similar inputs.
- Fitting a local linear model.
- Showing which features influenced that prediction.

Advantages:

- Local explanations.
- Model-agnostic.

---

## Global Reconstruction

Goal:

- Explain the overall behavior of a model.

Rather than explaining one prediction:

- Explain how the entire model behaves.

---

## Model Distillation

### Soft Decision Trees

A neural network can be distilled into a soft decision tree.

Characteristics:

- Multiple paths remain possible.
- Probabilities flow through the tree.
- Internal nodes represent learned concepts.
- Leaf nodes represent output distributions.

Benefits:

- Easier visualization.
- Easier explanation.

---

## Dark Side of Reconstruction

Reconstructed explanations may be:

- Plausible
- Convincing

but not necessarily:

- Accurate
- Faithful

A model may appear to understand concepts it does not actually use.

---

# Visualization and Attribution

Two complementary approaches:

| Method | Question |
|----------|----------|
| Visualization | What input activates the model? |
| Attribution | What input caused a prediction? |

---

# Feature Visualization

## Goal

Determine:

> What kinds of inputs maximize a model's response?

### Object Recognition Example

For a class \(c\):

Find an image that maximizes:

\[
S_c(I)
\]

Optimization:

\[
\arg\max_I \left( S_c(I) - \lambda ||I||_2^2 \right)
\]

The generated image reveals what the model associates with that class.

---

## Neuron Visualization

Instead of visualizing a class:

Visualize:

- Individual neurons
- Channels
- Layers

Goal:

- Understand what patterns excite specific components.

---

## Diversity of Visualizations

A neuron may respond to:

- Multiple parts of a dog.
- Different visual patterns.
- Seemingly unrelated concepts.

Therefore:

- No single visualization fully explains a neuron.

---

# Attribution Methods

## Saliency Maps

Question:

> Which pixels contributed most to the prediction?

A saliency map highlights:

- Important image regions.
- Where the model is "looking."

---

## Smallest Sufficient Region (SSR)

Definition:

Smallest image region that still allows confident classification.

Purpose:

- Identify essential information.

---

## Smallest Destroying Region (SDR)

Definition:

Smallest image region whose removal causes classification failure.

Purpose:

- Identify critical evidence.

---

## Good Saliency Maps

A useful saliency map should:

- Preserve prediction when kept (SSR).
- Destroy prediction when removed (SDR).

---

## Weakness of Visualization

Visual explanations can be ambiguous.

Different users may interpret:

- Heatmaps
- Saliency maps
- Feature visualizations

in different ways.

---

# Faithfulness vs. Plausibility

## Important Trade-off

Many explanations optimize for:

- Human appeal

rather than:

- Truthfulness

---

## Human Explanations Are

### Contrastive
People ask:

> Why X instead of Y?

### Selective
People prefer:

- A few important causes.
- Not every possible cause.

### Socially Constructed
Explanations are adapted to the audience.

---

## Consequence

Post-hoc explanations may be:

- Plausible
- Useful

but not necessarily:

- Complete
- Faithful

---

# Understanding Models Through Intervention

## Observation vs. Intervention

### Observation

Observe patterns:

\[
P(Y|X)
\]

Problems:

- Correlation does not imply causation.
- Confounders exist.

---

### Intervention

Actively manipulate variables:

\[
P(Y|do(X))
\]

Benefits:

- Isolates causal effects.
- Reveals what actually changes outcomes.

---

# Direct Manipulation

## Manipulating Features

Change a feature value and observe:

- Prediction changes.
- Model sensitivity.

Purpose:

- Understand feature influence.

---

## Manipulating Inputs

Users modify their inputs to see:

- How the system interprets them.
- How predictions change.

Benefits:

- Better understanding.
- Better communication with AI systems.

---

# Interactive Prediction Exploration

Model accuracy alone is insufficient.

Users should explore:

### Partial Dependence

Questions such as:

> What happens if age increases?

> What happens if income decreases?

Users can:

- Adjust features.
- Observe prediction changes.

Benefits:

- Detect unreasonable behavior.
- Build trust.

---

## Limitation

Feature interactions complicate interpretation.

Two variables may jointly influence outcomes.

Changing one feature at a time may miss these interactions.

---

## Dark Side of Intervention

People may learn how to manipulate model outputs.

Example:

- Increasing a credit limit may improve a credit score.
- Actual repayment ability remains unchanged.

---

# Feedforward: Proactively Understanding AI

## What Is Feedforward?

Traditional explanations are retrospective.

Feedforward is proactive.

It shows:

- What the system is likely to do.
- How current actions affect future outcomes.

---

## Gesture Recognition Example

A gesture recognizer predicts:

- Multiple possible future gestures.

As the user starts drawing:

- Several paths appear.
- One path becomes increasingly likely.
- Other paths disappear.

Benefits:

- Guides users.
- Helps users learn system expectations.

---

## Managing Complexity

Too much feedforward can become distracting.

Solution:

- Gradually reduce detail over time.

### Why?

Novice users:
- Need more guidance.

Expert users:
- Need less guidance.

Feedforward should disappear as confidence increases.

---

# Future Question

Can generative AI provide feedforward?

Examples:

- Large Language Models (LLMs)
- Text-to-image systems

Potential goal:

- Show likely future outputs before generation is completed.

---

# Summary: Design Considerations for Model Interpretability

## Interpretability > Explainability

Whenever possible:

- Use inherently interpretable models.
- Avoid relying solely on explanations.

---

## Good Explanations Are Contrastive

Prefer:

> Why X instead of Y?

over:

> Why X?

---

## Trade-off: Understandability vs. Completeness

More details:

- Higher completeness
- Lower understandability

Fewer details and more visuals:

- Higher understandability
- Lower completeness

---

## Final Takeaway

Effective model interpretability requires balancing:

- Accuracy
- Faithfulness
- Simplicity
- User needs
- Time constraints
- Motivation

The best explanation is not necessarily the most complete one—it is the one that helps the intended audience understand and act appropriately.