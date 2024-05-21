# Regex to NFA and DFA Converter

This repository contains a command-line tool and associated scripts for converting a regular expression to its corresponding Non-deterministic Finite Automaton (NFA) using Thompson's construction algorithm, and subsequently minimizing the NFA to a Deterministic Finite Automaton (DFA). The tool is designed as part of a programming assignment for the Compilers and Languages course at Cairo University's Faculty of Engineering, Computer Engineering Department.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)


## Description

![image](https://github.com/AhmedYasser20/Regex-to-NFA-and-DFA-Converter/assets/93765400/81138c8d-40c6-4312-bd70-fb33eb2fba8a)

This project implements a command-line tool to:
1. Convert a regular expression into a Non-deterministic Finite Automaton (NFA) using Thompson's construction algorithm.
2. Convert the generated NFA into a minimized Deterministic Finite Automaton (DFA).

Both conversions produce JSON files representing the states and transitions of the automata. Additionally, the tool outputs graphical representations of the NFA and DFA using a graphics library.

## Features

- **Regular Expression to NFA Conversion:** Converts a given regular expression into an NFA, validating the expression before transformation.
- **NFA to DFA Minimization:** Converts the NFA into a minimized DFA.
- **JSON Output:** Outputs the states and transitions of both NFA and DFA in a specified JSON format.
- **Graphical Representation:** Generates images of the NFA and DFA graphs, distinguishing between accepting and non-accepting states.
- **Google Colab Integration:** A ready-to-use Google Colab notebook for running the tool and generating outputs.

## Installation

To install and run the tool locally, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/username/regex-to-nfa-dfa.git
    cd regex-to-nfa-dfa
    ```

2. Create a virtual environment and activate it:
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

### Command-Line Interface

To convert a regular expression to an NFA and minimize it to a DFA, use the following commands:

1. **Convert Regular Expression to NFA:**
    ```bash
    python convert_to_nfa.py "[A-Za-z]+[0-9]*"
    ```

2. **Convert NFA to Minimized DFA:**
    ```bash
    python minimize_nfa.py path/to/nfa.json
    ```

### Google Colab

To use the tool in Google Colab, follow these steps:

1. Open the provided Colab notebook: [NFA to DFA Converter](https://colab.research.google.com/drive/1z2lr8--9hYPoLuGCOUfTwex9yeWVnDOd?usp=sharing)
2. Run the notebook cells to upload your input regular expression or NFA JSON file.
3. The notebook will generate the JSON files and graphical representations for both the NFA and the DFA.

## Examples

### Example Regular Expression Conversion



**Output JSON (NFA):**
```json
{
  "startingState": "S0",
  "S0": {
    "isTerminatingState": false,
    "A": "S1",
    "B": "S0"
  },
  "S1": {
    "isTerminatingState": true,
    "A": "S1",
    "B": "S1"
  }
}
```

**Graphical Representation:**
![image](https://github.com/AhmedYasser20/Regex-to-NFA-and-DFA-Converter/assets/93765400/5ec9e6a0-48ce-4295-97b4-96413d283c1b)


### Example NFA Minimization



**Output JSON (DFA):**
```json
{
  "startingState": "S0",
  "S0": {
    "isTerminatingState": false,
    "A": "S1",
    "B": "S0"
  },
  "S1": {
    "isTerminatingState": true,
    "A": "S1",
    "B": "S1"
  }
}
```

**Graphical Representation:**
![image](https://github.com/AhmedYasser20/Regex-to-NFA-and-DFA-Converter/assets/93765400/ccb24177-c47e-4437-b777-41909b9b6916)



