+++
date = '2026-05-4T10:01:52-08:00'
draft = false
title = 'L6: Mixed-Initiative Interaction'
+++

### Overview
Mixed-Initiative Interaction refers to systems where both humans and AI contribute to decision-making and task completion. Instead of either the human or AI being fully in control, initiative is shared dynamically based on context, uncertainty, and user needs.

---

# 1. Introduction to Mixed-Initiative Interaction

## Example: Dasher (2000)

### What is Dasher?
- A zoomable text-entry interface.
- Users point toward desired letters rather than selecting them precisely.
- A language model predicts likely next characters.
- The interface continuously zooms toward predicted text.

### Key Idea
- Combines:
  - Human guidance (pointing)
  - AI prediction (language model)

### Why Important?
- Demonstrates an early form of AI-assisted interaction.
- Shows how AI can reduce user effort without removing user control.

### Main Takeaway
Mixed-initiative systems combine human input with AI predictions to accomplish tasks more efficiently.

---

## Example: Gesture Keyboards

### How They Work
- Users draw approximate gestures across letters.
- AI interprets intended words using:
  - Gesture patterns
  - Language models

### Benefits
- Faster text entry.
- Less precision required from users.
- AI handles ambiguity.

### Main Takeaway
Humans provide rough intent; AI resolves uncertainty.

---

# 2. Direct Manipulation vs. Interface Agents

## Direct Manipulation (Ben Shneiderman)

### Philosophy
Users directly control interfaces and operations.

### Examples
- Browsing Netflix manually.
- Clicking menus and buttons.

### Advantages
- Transparency
- User control
- Predictability

---

## Interface Agents (Pattie Maes)

### Philosophy
AI observes user behavior and proactively takes action.

### Examples
- Recommendation systems.
- Intelligent assistants.

### Advantages
- Reduced effort.
- Automation of repetitive tasks.

---

## The Debate

### Core Question
Should systems:
- Let users control everything?
- Or proactively help users?

### Modern Answer
Neither extreme is ideal.

### Solution
**Mixed-Initiative Interaction**
- Human and AI collaborate.
- Control shifts depending on context.

---

# 3. Horvitz's Mixed-Initiative Principles

## Definition of AI Initiative

AI Initiative = deciding:
- Whether AI should act.
- When AI should act.
- How AI should act.

### Goal
Create an elegant combination of:
- Automation
- User control

---

# Principle #1: Developing Significant Value-Added Automation

## Key Idea
AI should only automate tasks that provide meaningful benefits.

### Example
Meeting scheduling assistant:
- Reads emails.
- Suggests meeting times automatically.

### Benefits
- Reduces multiple manual steps.
- Eliminates context switching.

### Design Question
"What does AI do better than direct manipulation?"

### Main Takeaway
Automation must create genuine value rather than merely replacing existing actions.

---

# Principles #2–4: Costs, Benefits, and Uncertainty

## Principle #2
### Consider User Goal Uncertainty

AI rarely knows exactly what users want.

### Example
An email might mention:
- Meeting planning
- Casual conversation

AI must estimate the user's intention.

---

## Principle #3
### Consider User Attention

AI actions can interrupt users.

### Questions
- Is the user busy?
- Is now a good time?

### Goal
Reduce distraction.

---

## Principle #4
### Consider Costs and Benefits

AI actions should maximize expected benefit.

### Examples
Potential Benefits:
- Time savings
- Reduced workload

Potential Costs:
- Wrong actions
- Interruptions
- Annoyance

---

# Decision Making with Expected Utility

## Basic Rule

AI compares:

- Utility of acting
- Utility of not acting

### Decision

If:

EU(Action) > EU(No Action)

Then AI should act.

Otherwise:
- Wait
- Ask user
- Do nothing

---

## Probability-Based Initiative

AI estimates:

P(User Wants Action)

Then chooses among:

### Low Probability
- Do nothing.

### Medium Probability
- Ask user.

### High Probability
- Act automatically.

### Main Takeaway
AI initiative should be proportional to confidence.

---

# Example: AI Sentence Completion

## Scenario
User pauses while writing.

### Question
Should AI complete the sentence?

---

## Step 1: Estimate User Need

Signal:
- Pause duration

Hypothesis:
- Longer pauses indicate greater need for help.

---

## Step 2: Estimate Utilities

Consider:

### AI Acts Correctly
High value.

### AI Acts Incorrectly
Distraction.

### AI Doesn't Act When Needed
Missed opportunity.

---

## Step 3: Determine Threshold

Compute a threshold probability P*.

### If
P(Need Help) > P*

AI acts.

### Otherwise
AI waits.

---

# Multi-Level Initiative

Instead of binary choices:

### Option 1
Do nothing.

### Option 2
Offer assistance.

### Option 3
Act automatically.

### Benefit
Creates smoother interaction under uncertainty.

---

# AI Uncertainty vs Human Uncertainty

## AI Uncertainty

AI is unsure:
- What user wants.
- Whether its action is correct.

---

## Human Uncertainty

User is unsure:
- What they want.
- What decision to make.

### Main Takeaway
Systems should account for both types of uncertainty.

---

# Timing of AI Actions

## Problem

Even when AI knows it should act:

### Question
When should it act?

---

## Poor Timing

Examples:
- Interrupting reading.
- Interrupting writing.
- Interrupting focused work.

---

## Possible Solutions

### User-Controlled Timing
Users specify delays.

#### Limitation
Users may not know optimal settings.

---

### Predictive Timing
AI learns:
- When users typically need help.
- When users manually invoke assistance.

Then acts slightly earlier.

---

## Main Takeaway

Correct timing is as important as correct action.

---

# Summary of Principles #2–4

### AI should:
- Model user goals.
- Model user attention.
- Consider costs and benefits.
- Account for uncertainty.
- Learn optimal timing.

---

# Principles #5, #6, and #9:
# Handling Uncertainty Through Collaboration

---

## Principle #5:
### Use Dialog to Resolve Uncertainty

When AI lacks information:

Ask users.

### Example
AI knows a meeting should happen.

But doesn't know:
- Date
- Time

Solution:
- Open calendar.
- Let user choose.

### Main Takeaway
Dialog can efficiently resolve uncertainty.

---

## Principle #6:
### Allow Direct Invocation and Termination

Users should always be able to:

- Start AI actions.
- Stop AI actions.

### Example
Multiple ways to activate Siri:
- Voice
- Button press

### Main Takeaway
Maintain user control.

---

## Principle #9:
### Support Human-AI Collaboration

AI outputs are often incomplete.

Users should be able to:
- Edit
- Refine
- Improve results

### Main Takeaway
AI should support collaboration rather than replacement.

---

# Summary of Principles #5, #6, and #9

Design systems so users can:

- Decide when AI participates.
- Resolve uncertainty through dialog.
- Modify AI outputs.
- Maintain control over automation.

---

# Principles #7 and #8:
# Minimize Errors Through Graceful Automation

---

## Principle #7:
### Minimize Cost of Wrong Predictions

AI will occasionally be wrong.

### Design Strategies

#### Easy Undo
Allow users to reverse actions.

#### Easy Cancellation
Allow users to stop automation.

#### Automatic Expiration
Suggestions disappear if ignored.

### Goal
Reduce consequences of mistakes.

---

## Principle #8:
### Scope Automation to Match Confidence

AI should only automate what it knows.

### Example

AI knows:
- Meeting week

AI doesn't know:
- Exact date
- Exact time

Instead of guessing:
- Open week view calendar.
- Let user choose details.

### Main Takeaway

❌ Automate everything

✅ Automate only what AI is confident about

---

# Summary of Principles #7–8

### Design AI to:
- Fail gracefully.
- Support undo.
- Limit automation to confident decisions.
- Let humans complete uncertain parts.

---

# Principles #10–12: Additional Considerations

## Principle #10:
### Socially Appropriate Behavior

AI should behave like a helpful assistant.

Examples:
- Polite responses.
- Appropriate interruptions.
- Respectful communication.

---

## Principle #11:
### Maintain Working Memory

AI should remember recent interactions.

Benefits:
- Reduced repetition.
- More natural conversations.
- Better context awareness.

---

## Principle #12:
### Continue Learning

AI should improve through observation.

Examples:
- Learn preferences.
- Learn habits.
- Adapt timing and suggestions.

---

# Final Summary: Mixed-Initiative UI Principles

## 1. Provide Meaningful Automation
Only automate tasks that create real value.

## 2. Consider Uncertainty
Estimate user goals and confidence levels.

## 3. Consider Attention and Timing
Act when help is useful, not disruptive.

## 4. Use Dialog
Ask users when uncertainty is high.

## 5. Preserve User Control
Allow manual invocation and termination.

## 6. Support Collaboration
Let users refine AI-generated outputs.

## 7. Reduce Error Costs
Provide undo and cancellation mechanisms.

## 8. Scope Automation
Only automate what AI is confident about.

## 9. Behave Socially
Act like a helpful assistant.

## 10. Remember Context
Maintain short-term interaction memory.

## 11. Learn Over Time
Adapt to users' needs and preferences.

---

# Key Design Philosophy

The central idea of mixed-initiative interaction is:

> AI should not replace human decision-making, nor should humans do everything themselves. The most effective systems dynamically share initiative, allowing AI and humans to contribute according to their strengths.