# [**Code of FOCED – Formal Object-Centric Event Data Pipeline**](https://arxiv.org/abs/2511.07263) accepted in [**1st International Workshop on Data-Centric AI for Intelligent Agents
**](https://dcai4ia.univ-tours.fr/)

**FOCED** is a Python and Alloy project for transforming **XES** or **OCEL** event logs into a **Formal Object-Centric Event Data (FOCED)** model.
It validates logical constraints and loads the result into **Neo4j** for graph-based analysis.

## 🔍 Features

* Parses **XES** and **OCEL JSON** logs using the [`pm4py`](https://pm4py.fit.fraunhofer.de/) library
* Normalizes data into an **object-centric schema** (`events`, `objects`, `event_object`)
* Enforces **Alloy-based logic** for timestamps, attributes, and object links
* Exports processed data to **Neo4j** with automatic indexing
* Includes example **Cypher queries** for exploration
* Saves validated backups as **JSON**

## 📂 Input Types

| File Type                  | Description                      |
| -------------------------- | -------------------------------- |
| `.xes`                     | Standard XES event logs          |
| `.jsonocel` / `.ocel.json` | OCEL (Object-Centric Event Logs) |


## Core Model Components

| Component        | Description                        |
| ---------------- | ---------------------------------- |
| **Event**        | `{id, activity, timestamp, attrs}` |
| **Object**       | `{id, type, attrs}`                |
| **Event_Object** | `{event_id, object_id, role}`      |

## Alloy Models

| File                             | Description                                          |
| -------------------------------- | ---------------------------------------------------- |
| `FOCED_Alloy_MM.als`             | Defines the metamodel for event–object relationships |
| `Enhanced_FOCED_Constraints.als` | Adds structural and temporal constraints             |

Both can be opened in **Alloy Analyzer** for validation and experimentation.

## Installation and Setup

```bash
# Create environment
conda create -n foced python=3.12

# Activate environment
conda activate foced

# Clone repository
git clone https://github.com/sabalati/FOCED.git

cd FOCED

# Install dependencies
pip install -r requirements.txt
```

## Running FOCED

1. Open **FOCED.py** and specify:

   * Path to your **input log file** (`.xes` or `.ocel.json`)
   * Your **Neo4j username** and **password**

2. Run the pipeline:

```bash
python FOCED.py
```
This will:
* Parse and normalize your event log
* Validate it using Alloy constraints
* Load the resulting **Formal OCED** graph into Neo4j

## Output

* Validated **object-centric event model** stored in Neo4j
* **JSON backup** of the processed data
* Example **Cypher queries** included for further analysis in paper

## Citation

If you use FOCED in academic work, please cite the paper
```
@misc{latif2025alloydrivenverificationobjectcentricevent,
      title={Alloy-Driven Verification of Object-Centric Event Data: From Temporal Logic to Knowledge Graphs}, 
      author={Saba Latif and Huma Latif and Touseef Ur Rehman and Muhammad Rameez Ur Rahman},
      year={2025},
      eprint={2511.07263},
      archivePrefix={arXiv},
      primaryClass={cs.FL},
      url={https://arxiv.org/abs/2511.07263}, 
}
```
