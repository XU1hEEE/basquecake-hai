+++
date = '2026-05-20T10:01:52-08:00'
draft = false
title = 'L7: Autonomy, Trust & Reliance'
+++

### Overview
This lecture examines three critical human factors in AI systems:

1. **Autonomy** – users' ability to maintain control and make independent decisions.
2. **Trust** – users' belief that AI will help achieve their goals.
3. **Reliance** – the extent to which users act on AI recommendations.

The goal is not simply to maximize trust or automation, but to design AI systems that support **appropriate autonomy, trust, and reliance**.

---

# Part 1: Human Autonomy

## What Limits Human Autonomy?

Human autonomy refers to a user's ability to make decisions and maintain meaningful control while interacting with AI.

Four major factors influence autonomy:

### 1. System Capability

A system must be capable enough to help users accomplish tasks.

#### Problem
- Low-capability systems cannot effectively support users.
- Users become constrained by what the AI can do.

#### Design Implications
- Scope AI functionality appropriately.
- Clearly communicate system limitations.
- Provide alternative options when AI cannot help.

---

### 2. System Complexity

More capable systems are often more complex.

#### Example
- AutoCAD
- Photoshop

Complex software does not automatically remove autonomy because users can learn how to use it effectively.

#### Capability vs. Complexity Trade-off

More capability often means:
- More features
- More complexity

Less complexity often means:
- Fewer features
- Reduced capability

### Key Challenge

Balance:

- Capability
- Complexity
- User autonomy

---

## Levels of Autonomy

### Example: Autonomous Vehicles

Higher autonomy:
- Less user effort
- Less manual control

Lower autonomy:
- More user control
- Higher cognitive workload

### Design Principle

Introduce autonomy gradually.

#### For Users

Start with:
- Small set of capabilities
- Low complexity

Then:
- Increase functionality progressively
- Allow users to learn over time

#### For Designers

Build systems incrementally:
- Start with core features
- Add capabilities as needs expand
- Continuously involve users

---

## Encourage Exploration

Exploration helps users learn system capabilities.

Benefits:
- Reduces perceived complexity
- Improves understanding
- Supports autonomy

Example:
- Exploring latent editing directions in GAN-based image generation systems.

---

## Misrepresentation

### Definition

Misrepresentation occurs when AI presents inaccurate information as if it were correct.

### Example

ChatGPT confidently generating incorrect information.

### Consequences

Users lose the ability to judge:

- When AI is correct
- When AI should be trusted

### Design Goal

Help users detect:
- Errors
- Uncertainty
- Hallucinations

---

## System Fluidity

### Definition

AI systems change over time.

Both:
- User goals evolve
- AI capabilities evolve

### Examples

Older versions of ChatGPT:
- Knowledge cutoff limitations

Newer models:
- Frequent updates
- Behavioral changes

### Challenge

Users struggle to predict:

- Current capabilities
- Future behavior

### Design Goal

Inform users whenever significant changes occur.

---

# Enhancing Autonomy

## Capability

- Match AI scope to actual capability.
- Explain limitations.
- Provide alternatives.

## Complexity

- Reduce unnecessary features.
- Reduce interaction steps.
- Use progressive autonomy levels.

## Representation

- Minimize misinformation.
- Enable users to detect errors.

## Fluidity

- Communicate updates and changes.

---

## Can Users Have Too Much Autonomy?

An important design question:

> Is maximum autonomy always desirable?

Too much autonomy may:

- Increase workload
- Increase complexity
- Require excessive expertise

The optimal design balances:

- User control
- Automation support

---

# Part 2: Measuring Autonomy

## Self-Report Measures

Ask users directly:

Examples:
- "I felt in control."
- "Who caused the outcome?"

### Advantages

- Easy to administer
- Captures perceived autonomy

### Limitations

- Users may misjudge their own control.

---

## Intentional Binding

### Definition

Measure perceived time between:

Action → Outcome

### Interpretation

Shorter perceived intervals indicate:

- Stronger sense of agency
- Greater autonomy

### Importance

One of the most rigorous experimental measures.

---

## Behavioral Measures

Observe actual behavior.

Examples:

### Override Rate

How often users reject AI recommendations.

### Exploration

Whether users investigate alternatives.

### Intervention

Whether users actively step in rather than passively accept AI output.

---

## Causal Measurement

Manipulate system properties and observe effects.

Examples:

### Lower Reliability

→ Lower autonomy

### Increased Latency

→ Lower autonomy

### Increased Automation

→ Lower autonomy

---

## Assistance Threshold Tests

Gradually increase AI assistance.

Goal:
- Identify point where users begin losing autonomy.

---

# Part 3: Understanding Trust

## What Is Trust?

Trust is:

> The attitude that an agent will help achieve a person's goals under conditions of uncertainty and vulnerability.

Two key elements:

### Vulnerability

The user has something at risk.

### Anticipation

The user can predict the consequences of AI actions.

---

## Trust Leads to Action

Trust is not merely a belief.

Trust influences decisions such as:

- Delegating tasks
- Following recommendations
- Depending on automation

---

# Trust vs Trustworthiness

## Trust

A human attitude toward AI.

### Example

A user believes ChatGPT is always correct.

---

## Trustworthiness

A property of the AI system.

### Example

An AI system consistently provides accurate information.

---

## Important Insight

### Unwarranted Trust

Users trust untrustworthy AI.

Example:
- Believing hallucinated outputs.

### Distrust of Trustworthy Systems

Users reject reliable AI due to:

- Algorithm aversion
- Poor understanding

---

# Contractual Trust

Trust based on explicit expectations.

### Definition

Users believe AI will follow a specific contract.

### Example

Constitutional AI

Users trust that the system will:
- Follow predefined principles
- Behave consistently

---

# Intrinsic vs Extrinsic Trust

## Intrinsic Trust

Trust based on understanding the reasoning process.

### Example

"I trust these doctors because they cite evidence."

Requirements:

- Transparency
- Interpretability
- Understandable reasoning

---

## Extrinsic Trust

Trust based on external validation.

### Example

"I trust these doctors because of their track record."

Sources include:

- Benchmarks
- Reputation
- Certifications
- Historical performance

---

# Explainability Case Study

## AI Radiology Systems

Modern AI can interpret chest X-rays nearly as well as radiologists.

### Challenge

Black-box models provide limited insight.

Result:

- Low comprehension
- Low trust
- Low adoption

---

## Solution

Create user interfaces that allow physicians to:

- Explore AI reasoning
- Understand predictions
- Verify findings

---

# Explanation vs Justification

## Explanation

Shows:

How AI reached a decision.

Supports:

- Intrinsic trust

Example:
- Saliency maps
- Feature importance

---

## Justification

Shows:

Why the decision is reasonable.

Supports:

- Extrinsic trust

Example:
- Statistical prevalence
- Benchmark evidence

---

# Part 4: Factors Influencing Trust

## AI Factors

### Purpose

Is AI being used appropriately?

Example:
- Using a general language model for diagnosis.

---

### Process

Is the AI's process suitable?

Example:
- Is next-token prediction appropriate for the task?

---

### Performance

Three dimensions:

#### Ability
Can AI help?

#### Reliability
Does AI make mistakes?

#### Predictability
Can users anticipate performance?

---

## Human Factors

### Analytic Trust

Based on reasoning and evidence.

---

### Analogical Trust

Based on previous experiences.

Example:
- Trusting a self-driving taxi because earlier rides were successful.

---

### Affective Trust

Based on emotions.

Example:
- Feeling uncomfortable letting a self-driving car transport a newborn baby.

---

# Three Layers of Trust

## 1. Dispositional Trust

Long-term tendency to trust technology.

Influenced by:

- Personality
- Age
- Culture
- Gender

Difficult to change.

---

## 2. Situational Trust

Specific to a particular interaction.

Influenced by:

- Task difficulty
- Workload
- Risk
- Context

---

## 3. Learned Trust

Developed through repeated interactions.

Influenced by:

- Reliability
- Predictability
- Past experiences

---

# Part 5: Measuring Trust

## Why Not Ask "Do You Trust AI?"

Trust is complex.

A single question often fails to capture:

- Vulnerability
- Context
- Reliance behaviors

---

## Behavioral Indicators

Trust can be measured through:

- Acceptance rates
- Override behavior
- Decision patterns

---

## Trust Vocabulary Scales

Researchers developed questionnaires using words associated with:

### Trust
- Reliable
- Dependable
- Competent

### Distrust
- Unreliable
- Unpredictable
- Deceptive

These scales produce more accurate trust measurements.

---

## Dynamic Trust Measurement

Trust changes over time.

Factors include:

- AI performance
- User experience
- Increased AI literacy

Researchers should measure trust repeatedly rather than only once.

---

# Part 6: Designing for Appropriate Trust

## Goal

Not:

❌ Maximize trust

Instead:

✅ Support appropriate trust

---

## Key Principle

Users should know:

- When to trust AI
- When not to trust AI

---

## Design Strategies

### Usability

Easy-to-use systems encourage appropriate trust.

---

### Transparency

Reveal:
- Logic
- Confidence
- Reliability

---

### User Control

Allow users to:
- Override AI
- Intervene
- Retain authority

---

# Part 7: Reliance and Overreliance

## Trust vs Reliance

### Trust

Attitude

### Reliance

Action

A user may:

- Trust AI but ignore it.
- Distrust AI but still follow it.

---

## Types of Reliance

### Type 1

Follow AI recommendations.

Example:
- Accept grammar correction.

---

### Type 2

Do nothing when AI gives no recommendation.

Example:
- Assume no errors exist because AI found none.

---

# Overreliance

## Definition

Users accept incorrect AI recommendations.

Or:

Users follow AI when they would have performed better independently.

---

## Relationship to Autonomy

Low autonomy often leads to:

- Passive acceptance
- Reduced critical thinking
- Overreliance

---

# Overreliance vs Underreliance

## Overreliance

Trust AI too much.

Example:
- Accepting incorrect recommendations.

---

## Underreliance

Trust AI too little.

Example:
- Rejecting correct recommendations.

---

## Appropriate Reliance

Users:

- Accept correct recommendations.
- Reject incorrect recommendations.

---

# Factors Influencing Overreliance

## AI Literacy

Low AI literacy often leads to:

- Overestimating AI capability
- Excessive acceptance

---

## Expertise

### Low Expertise

Algorithmic susceptibility.

More likely to accept AI.

### High Expertise

Algorithmic aversion.

More likely to reject AI.

---

## Task Familiarity

Familiar users often:

- Trust themselves more
- Override AI more often

However explanations can sometimes increase overreliance.

---

## Explanations

Explanations increase reliance on:

- Correct answers
- Incorrect answers

Therefore explanations alone are insufficient.

---

## Sources

Providing sources helps users verify claims.

Result:

- Less reliance on incorrect outputs

---

## Anthropomorphism

Human-like AI can increase overreliance.

Users may incorrectly assume:

- Empathy
- Reasoning ability
- Human judgment

---

# Mitigating Overreliance

## During Onboarding

Learn about users':

- AI literacy
- Confidence
- Automation bias

Teach:

- AI strengths
- AI limitations
- Appropriate reliance

---

## During Regular Use

### Cognitive Forcing Functions (CFF)

Design interventions that force analytical thinking.

Examples:

- Delayed AI answers
- Uncertainty indicators
- On-demand explanations

---

### Real-Time Feedback

Warn users when:

- Confidence is low
- Uncertainty is high

Examples:
- Outlier detection
- Prediction variance

---

## Be Careful With Explanations

Explanations help only when:

- Predictions are correct
- Explanations accurately reflect reasoning

Risk:

A convincing explanation can make an incorrect answer appear trustworthy.

### Recommendation

Use explanations together with:

- Sources
- Confidence indicators
- Cognitive forcing functions

---

# Final Takeaways

## Autonomy

Users need meaningful control over AI systems.

Key threats:
- Limited capability
- Complexity
- Misrepresentation
- System changes

---

## Trust

Trust is an attitude developed under uncertainty.

Important distinctions:

- Trust ≠ Trustworthiness
- Intrinsic Trust ≠ Extrinsic Trust
- Appropriate Trust ≠ Maximum Trust

---

## Reliance

Reliance is observable behavior.

Goal:

- Accept correct AI advice.
- Reject incorrect AI advice.

---

## Core Design Principle

> The objective of Human-Centered AI is not to maximize automation, trust, or reliance. Instead, it is to help users maintain autonomy, develop appropriately calibrated trust, and rely on AI only when doing so improves decision-making.