Degree level: Master’s

# Project proposal

## 1. The problem and goal

(Explain the problem you want to solve and why it matters. Describe what you
want to improve, how you will measure improvement, and which limits or
requirements must be respected. A short example can help someone outside your
field understand the problem.)

**The problem and goal in my project:**

Bioinformatics tools are used to identify genes, viruses, DNA inversions, and other genomic features. Although these tools are tested by their developers, their performance may be affected by combinations of sequence characteristics that are not fully covered by standard benchmarks. The goal of my project is to develop an AI agent that investigates the reliability of a selected bioinformatics tool by designing experiments with synthetic or modified DNA sequences containing known biological features. For example, it could investigate whether repetitive DNA regions combined with sequencing errors affect the identification of a known genomic feature. I want to evaluate whether the agent can identify meaningful limitations using fewer experiments than brute-force testing methods. The project will initially focus on one tool and a small number of test sequences.

## 2. The simulator

(Describe a program or model that could simulate your system and calculate what
happens under different conditions. Explain what inputs it takes and what
results it produces. State whether it can run on your computer and accept inputs
in a text file, such as JSON or YAML. If you have not chosen a simulator yet,
name an option you want to explore and explain what you need to check.)

**The simulator in my project:**

I have not selected a specific tool yet. One option I would like to explore is minimap2, using its Python interface called mappy. It aligns DNA sequencing reads to reference sequences and is widely used in genomic analysis. Instead of a traditional simulator, I plan to use an existing bioinformatics tool together with a Python-based sequence generator as the computational ground. Starting from real bacterial reference sequences, the generator could introduce controlled modifications, such as repetitive regions or sequence variations. For a read-alignment tool, it could also generate synthetic sequencing reads with known origins and controlled sequencing errors. The selected tool would analyze these sequences, and its results would be compared with the known properties of the generated data. The process would accept inputs through Python, potentially using JSON to describe the experiments. With fixed inputs and random seeds, the results should be reproducible. Before selecting the tool, I need to check whether it can run quickly enough on my computer, which modifications are suitable for testing it, and whether the expected results can be defined objectively. I also need to determine which conditions have already been examined in published benchmarks.

## 3. The agent's role

(Explain what the language-model-based agent will decide or change, and how it
will use the simulator's results to choose its next action. If known, list the
variables it may change and their allowed ranges. Explain what you expect the
language model to contribute: could a simple program that tries different
options and picks the best result achieve the same goal? Include one question
you still need to answer.)

**The agent in my project:**

The agent will use biological knowledge and information about the selected tool's algorithm to develop hypotheses about conditions that may affect its accuracy. For example, if the tool fails to identify a known genomic feature in a repetitive region, the agent could investigate whether the problem is related to the repeat structure, sequencing errors, or a combination of both. It would design a follow-up experiment to distinguish between these explanations, run the tool again, and use the results to decide what to investigate next. The agent will select from predefined, biologically relevant modifications. Python functions will perform the modifications and verify that the generated sequences satisfy the required constraints. The specific parameters and their allowed ranges will depend on the selected tool. I plan to compare the agent with random or rule-based testing approaches, measuring how many valid and informative failure cases each approach identifies within the same number of experiments. The main open question is whether reasoning about biological and algorithmic mechanisms can help the agent identify meaningful limitations more efficiently than brute-force testing methods.

## Explain your project to someone outside your field

(Now describe your whole project again, as if you were explaining it to someone
from another field who has no background in your topic. For example, if you
study chemical engineering, imagine explaining it to a physicist; if you study
aeronautical engineering, imagine explaining it to someone in medicine; if you
study data science, imagine explaining it to a materials engineer. In one or two
short paragraphs, connect all three parts: the problem you want to solve, how
the simulator helps you test ideas, and what the agent will decide or change.
Use everyday language, explain any technical terms you need, and avoid
unexplained abbreviations. Do not simply copy your answers above.)

**My project in simple words:**

Bioinformatics tools are widely used to identify genomic features, including genes, viral sequences, and structural changes in DNA. Although these tools undergo validation, their accuracy may depend on several interacting characteristics of the analyzed sequences. I hypothesize that some combinations of conditions may not be fully evaluated during their development. My project aims to develop an AI agent that investigates these limitations through controlled experiments. Using DNA sequences with known properties, the agent will propose biologically-driven modifications and test how they affect the predictions of a selected bioinformatics tool. Instead of changing parameters randomly, it will use the results of previous experiments to form hypotheses and decide what to investigate next. The goal is to evaluate whether this approach can identify useful limitations more efficiently than automated brute-force testing methods.
