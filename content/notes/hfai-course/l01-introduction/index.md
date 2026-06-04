+++
date = '2026-03-30T10:01:52-08:00'
draft = false
title = 'L1: Introduction to Artificial Intelligence'
+++

### Defining AI
*   AI is defined as algorithms performing tasks or behaviors that a human would reasonably deem to require intelligence.
*   The term is often used synonymously with "machine learning" and "algorithms".
*   An example of AI application is predicting a house's price based on inputs like size, family size, number of bedrooms, walkability, zip code, wealth, and school quality.

### Early Influences and Foundations
*   **Cybernetics (1948):** Introduced by Norbert Wiener, it focused on control and communication in animals and machines.
*   Cybernetics introduced concepts like feedback loops and adaptive systems, which heavily influenced early AI research.
*   **Neuroscience (~1900):** Identified the neuron as the brain's basic functional unit. 
*   The Hodgkin-Huxley model (1952) described electrical signal propagation through neurons, inspiring neuromorphic computer architecture designed to operate like neural systems.
*   **McCulloch-Pitts Neurons (1943):** Proposed by Warren S. McCulloch and Walter Pitts to simulate brain function using simple, interconnected, binary cells.
*   **Perceptrons (1950s):** Developed by Frank Rosenblatt, this concept takes continuous or binary inputs, weighs them to reflect importance, and produces a binary output based on a threshold. 
*   The perceptron formula dictates the output based on the weighted sum of inputs: 
$$output=\begin{cases}0 & if\sum_{j}w_{j}x_{j}\le threshold\\ 1 & if\sum_{j}w_{j}x_{j}>threshold\end{cases}$$
*   **Turing's Paper (1950):** Alan Turing asked "can machines think?" and proposed the Turing test to determine if a machine is indistinguishable from a human.

---

## The Birth and Evolution of AI

### The Dartmouth Summer Research Project (1956)
Organized by John McCarthy, Marvin Minsky, Claude Shannon, and Nathaniel Rochester, this two-month project aimed to develop the idea of a "thinking machine". They established seven key aspects of AI:
*   **Automatic Computers:** Writing programs that maximize computing resources.
*   **Language:** Programming computers to use and deduce meaning from language.
*   **Neuron Nets:** Arranging hypothetical neurons to form concepts.
*   **Calculation Size Theory:** Measuring the complexity of calculating problem solutions.
*   **Self-improvement:** Enabling truly intelligent machines to improve themselves.
*   **Abstractions:** Classifying ways to abstract problems for machines to solve.
*   **Randomness and Creativity:** Using controlled randomness to enable creative thinking.

### Early AI Achievements (1950s-1960s)
| Year | Achievement | Description |
| :--- | :--- | :--- |
| **1955** | Simon, Newell, and Shaw's AI Logic Theorist | Showed machines could perform human-like symbolic reasoning to prove mathematical theorems. |
| **1959** | Samuel's Checkers-Playing Program | Demonstrated machines could learn from experience and improve performance beyond hand-coded rules. |
| **1964** | Daniel Bobrow's Algebra Solving AI | Showed machines could translate natural language word problems into formal equations to solve them. |
| **1966** | Joseph Weizenbaum's ELIZA Chatbot | Created a mock Rogerian psychotherapist chatbot. |

### AI Winters and Modern Resurgence
*   The 1960s and 1970s saw over-optimism, with predictions that machines would do any human work within 20 years.
*   This hype cycle led to two "AI Winters" (1970s and 1990s) where popularity dropped.
*   Explosive growth returned with achievements like Deep Blue beating Gary Kasparov (1997), the development of Deep Learning (2006), IBM's Watson winning Jeopardy (2011), and AI beating Go world champions (2016).

---

## Human Factors in AI (HFAI)

### The Problem with Modern AI
*   Modern AI is data-driven and functions as a 'black box', meaning users often do not understand how or why models work or fail.
*   **Extrinsic Causes:** AI relies on data, which is a double-edged sword ("garbage in, garbage out") often plagued by bias.
*   Examples of failures include Amazon's biased recruiting tool, Google Photos mislabeling images, self-driving Uber crashes, racist chess chats, and biased court sentencing.
*   **Intrinsic Causes:** There is a general oblivion to human factors in AI development.

### Understanding Human Factors
*   Human factors consider human abilities, limitations, and characteristics in the design process.
*   The goals are to reduce human error, increase productivity, and enhance safety, comfort, and enjoyment.
*   HFAI studies aspects throughout AI's lifecycle that either influence or are influenced by humans.

### Machine Learning Pipeline & HFAI Topics
The machine learning pipeline involves Data Collection, Feature Engineering, Model Training, Evaluation, Deployment, Monitoring, and Maintenance. HFAI integrates into this pipeline through various topics:
*   **Human Intelligence:** Comparing AI to human neurobiology and cognitive theories.
*   **Data Collection & Annotation:** Addressing inaccuracies, biases, and annotation quality.
*   **Feature Visualization & Engineering:** Understanding the 'what, why, and how' of feature transformation.
*   **Model Interpretability:** Designing interactions for explainable AI and understanding user needs.
*   **Mixed-Initiative Interaction:** Applying principles of interaction between humans and AI.
*   **Autonomy & Reliance:** Mitigating overreliance on AI and understanding factors affecting human autonomy.
*   **Fairness & Bias:** Assessing and mitigating biases through technical, design, and regulatory approaches.
*   **User Research Methods:** Designing studies to evaluate system designs.
