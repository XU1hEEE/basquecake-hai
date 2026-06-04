+++
date = '2026-04-20T10:01:52-08:00'
draft = false
title = 'L4: Feature Visualization & Engineering'
+++

## Data Tables and Network Data

### What Is a Data Table?
- A data table consists of:
  - **Rows (tuples)** representing entities.
  - **Metadata (features)** describing those entities.

#### Example: Distance Between Cities
- Tuple: `(start city, end city)`
- Metadata: distance between the two cities.
- Each row represents a different city pair and associated information.

### Network Data → Data Table
A network of documents can be transformed into a data table.

- **Row (tuple):** a document.
- **Metadata:**
  - Document length.
  - Links to other documents.

---

# Visualization Pipeline

## Raw Data → Data Table → Visual Structures → Views

### Visual Structure

A visual structure augments spatial space with graphical elements to encode information.

Three components:

### 1. Spatial Substrate
Determines:
- Where data appears in x/y space.
- Which layer it occupies (z dimension).

### 2. Marks
Visual representations such as:
- Points
- Lines
- Areas
- Volumes

### 3. Graphical Properties
Maps data properties onto visual properties.

Examples:
- Color
- Size
- Shape
- Position

---

## Good Visualization Mapping

### Criterion 1: "No More"
A visualization should display:
- The intended information.
- No unnecessary information.

Questions:
- What is the visualization trying to communicate?
- Does it avoid showing irrelevant information?

### Criterion 2: Effectiveness
A good visualization should:
- Be fast to interpret.
- Convey distinctions clearly.
- Reduce interpretation errors.

Example:
- A sine wave is easier to understand using a **line chart** than color coding.

---

## Visual Variables

### Spatial Position
Spatial position is one of the strongest visual encoding methods.

Example:
- Tufte's visualization of the Challenger disaster.

### Bertin's Visual Variables

Important lessons:

- Relative size is one of the most useful visual variables.
- Size and position communicate quantitative information most accurately.
- Light-to-dark value communicates order better than color changes.
- Color, shape, and orientation are best for grouping and association.

---

# Views and User Interaction

## Views

Views determine:
- How visual structures are presented.
- How users interact with them.

### Three Common View Transformations

#### 1. Location Probe
Allows users to inspect specific data points.

Examples:
- Hovering to reveal a tooltip.
- Clicking to expand details.

#### 2. Viewport Control
Allows users to:
- Zoom
- Pan
- Filter
- Navigate large datasets

#### 3. Distortion
Creates focus + context visualizations.

Characteristics:
- Area of interest is emphasized.
- Remaining information is distorted but still visible.

Examples:
- Hyperbolic trees.
- Perspective walls.

Benefits:
- Maintain context while highlighting details.

---

## Interaction Throughout the Pipeline

User interaction can occur at every stage:

### Raw Data → Data Tables
- Filtering raw data.
- Selecting subsets.

### Data Tables → Visual Structures
- Choosing visual encodings.
- Selecting marks and mappings.

### Visual Structures → Views
- Zooming.
- Manipulating.
- Filtering.
- Exploring.

---

# Feature Visualization

## Purpose

Feature visualization helps people:

- Perceive patterns.
- Build intuition.
- Understand what information is useful for learning.

Visualization should precede feature engineering.

---

# Case Studies

## Visualizing Electromagnetic (EM) Noise

Visualization can reveal:
- Signal patterns.
- Device-specific signatures.
- Distinguishing features useful for ML.

---

## IMU Gesture Recognition

### Raw Data
- Accelerometer readings over time.

Visualization helps identify:
- Peaks.
- Temporal patterns.
- Gesture signatures.

### Knock-Knock Gesture Detection

Using a wrist-worn IMU:

- Accelerometer and gyroscope data are visualized.
- Certain axes show clear peaks during the gesture.
- These peaks become candidate features.

---

## Face-Touch Detection

Visualization reveals:

- Face-touching activities generate distinct IMU patterns.
- Overlaying X/Y/Z sensor values makes these patterns visible.
- Differences become features for classification.

---

## Object Recognition

Visualization helps determine what the model actually uses.

Example:
- Recognizing a printer.

Useful features:
- Printer appearance.
- Environmental context.

Less useful features:
- Temporary objects.
- Printed papers.
- Staplers.

---

## Tornado Plot for Text Classification

Goal:
- Determine whether reviews are positive or negative.

Approach:
- Find words frequently occurring in positive reviews.
- Visualize influential words.

Observation:
- Certain words strongly indicate sentiment.

---

## Feature Contribution Visualization

Example:
- Predicting pneumonia risk.

Visualization shows:
- Relationship between patient features and predicted risk.
- Importance of individual features.
- Distribution of actual data points.

Benefit:
- Understand how each feature contributes to predictions.

---

# Feature Engineering

## Data Is Not Necessarily a Feature

Raw data often requires transformation.

### Example: Housing Prices

Using:
- Length of a square lot

may not fit a linear model well.

Instead use:

Area = Length²

Result:
- Area becomes the useful feature.
- Length remains raw data.

---

# Types of Features

## Numeric Features
Represented by numbers:

- Integers
- Floating-point values

Examples:
- Age
- Income
- Temperature

---

## Categorical Features

### Nominal
No natural ordering.

Examples:
- Gender
- Ethnicity
- Country

### Ordinal
Natural ordering exists.

Examples:
- Education level
- Age groups
- Income brackets

---

# Numeric → Categorical Conversion

## Binning / Bucketing

Example:

Age →

- Child
- Teen
- Adult
- Senior

### Reasons

#### Noise Reduction
Small differences may not matter.

#### Capturing Nonlinearity
Outcomes may change abruptly across groups.

#### Outlier Reduction
Extreme values have less influence.

---

# Categorical → Numeric Conversion

Most ML algorithms require numeric inputs.

## Ordinal Encoding

For ordered categories:

| Category | Value |
|-----------|---------|
| Low | 1 |
| Medium | 2 |
| High | 3 |

---

## Problems with Simple Integer Encoding

Example:

- E 56th Street → 56
- E 57th Street → 57

Problems:

- Assumes equal spacing between categories.
- Cannot represent multiple categories simultaneously.
- Introduces artificial relationships.

---

## One-Hot Encoding

Create one feature per category.

Example:

| Street 56 | Street 57 | Street 58 |
|------------|------------|------------|
| 1 | 0 | 0 |

Advantages:

- No false ordering.
- Multiple categories can be represented simultaneously.

---

# Feature Transformation

## Creating New Features

New features can be derived from existing ones.

### Concrete Strength Example

Baseline model:

- MAE = 8.232

Hypothesis:

Material ratios matter.

Created features:

- FineAggregate / CoarseAggregate
- Aggregate / Cement
- Water / Cement

Result:

- MAE improved to 7.948

Key lesson:

> Understanding domain knowledge often leads to better features.

---

# Feature Representation

After visualization reveals patterns, features must be represented computationally.

## Descriptive Statistics

For a signal \(S\):

### Basic Statistics
- Maximum
- Minimum
- Sum
- Mean
- Median

### Variability Measures
- Standard deviation
- Coefficient of variation
- Mean absolute deviation
- Median absolute deviation

### Temporal Features
- Zero crossings

---

## Distribution Features

### Histogram
Captures distribution shape.

### Skewness
Measures asymmetry.

### Kurtosis
Measures tail heaviness.

---

## Signal Features

### Energy
Total signal magnitude.

### Log Energy
Log-transformed signal energy.

### Signal Power
Average energy.

### Signal Magnitude Area (SMA)
Combined magnitude across axes.

### Peak-to-Peak Amplitude
Difference between max and min.

### Time Between Peaks
Captures periodic behavior.

---

## Important Principle

Do **not** blindly compute every feature.

Recommended workflow:

1. Visualize the data.
2. Identify meaningful patterns.
3. Choose representations that describe those patterns.

---

# Feature Selection

## Why Not Use Every Feature?

Problems:

### Overfitting
Models may learn noise.

### Redundant Information
Extra computation with little benefit.

### Non-informative Features
Can reduce performance.

---

# Human Bias in Feature Selection

## Why Human Selection Helps

Humans exploit useful cognitive biases:

### Recency Bias
Recent information often matters more.

### Saliency Bias
Attention naturally focuses on prominent information.

### Memory Constraints
Humans tend to ignore low-value information.

---

## Why Human Selection Can Be Harmful

Example:
Predicting job success using:

- University prestige
- GPA
- Employer brand name

Potential issues:

- Socioeconomic bias
- Educational-system bias
- Brand halo effects

---

# Experimental Feature Selection

Instead of asking:

> Which features feel right?

Ask:

> Which features reduce uncertainty about the outcome?

---

## Ablation Analysis

Procedure:

1. Remove a feature.
2. Retrain the model.
3. Measure performance loss.
4. Restore the feature.

Large performance drops imply importance.

---

## Statistical Methods

### Chi-Square Selection
Tests dependence between feature and class.

### Correlation Analysis
Measures relationships between variables.

---

# Mutual Information

## Definition

Mutual Information (MI) measures:

> How much knowing feature X reduces uncertainty about outcome Y.

---

## Example

House price prediction:

Feature:
- Exterior quality

Observation:
- Better exterior quality makes price more predictable.

Therefore:
- High mutual information.

---

## Advantages

Unlike correlation:

- Captures nonlinear relationships.
- Detects broader dependencies.

---

## Interpretation

### Lower Bound
- 0 = independent variables

### Upper Bound
- No theoretical maximum

Rule of thumb:
- Values around 2.0 are considered very high.

---

## Example Ranking

Predicting automobile price:

| Feature | MI Score |
|-----------|-----------|
| curb_weight | 1.54 |
| highway_mpg | 0.95 |
| length | 0.62 |
| fuel_system | 0.49 |
| stroke | 0.39 |
| num_of_cylinders | 0.33 |

Higher scores indicate more informative features.

---

# Limitations of Mutual Information

## Feature Interactions

A feature may become valuable only when combined with another feature.

Mutual information evaluates features individually and may miss such interactions.

---

## Learning Limitations

A strong feature does not guarantee:

- The model can use it effectively.
- The model architecture can learn the relationship.

---

# Key Takeaways

## Visualization
- Transform raw data into visual structures.
- Use effective mappings and visual encodings.
- Support exploration through interaction.

## Feature Engineering
- Convert data into meaningful features.
- Apply transformations and representations.
- Use domain knowledge whenever possible.

## Feature Selection
- Avoid unnecessary features.
- Evaluate feature usefulness experimentally.
- Use mutual information and statistical methods.
- Verify findings through visualization and model evaluation.

> Visualization remains essential throughout the entire feature engineering and feature selection process.