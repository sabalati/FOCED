FOCED — Formal Object-Centric Event Data Pipeline

FOCED is a Python and Alloy project for transforming XES or OCEL event logs into a Formal Object-Centric Event Data model.
It validates logical constraints and loads the result into Neo4j for graph-based analysis.

Features

Parses XES and OCEL JSON logs using the pm4py library

Normalizes data into an object-centric schema (events, objects, event_object)

Enforces Alloy-based logic for timestamps, attributes, and object links

Exports processed data to Neo4j with automatic indexing

Includes example Cypher queries for exploration

Saves validated backups as JSON

Input Types

.xes — standard XES logs

.jsonocel or .ocel.json — OCEL object-centric logs

Core Model
Component	Description
Event	{id, activity, timestamp, attrs}
Object	{id, type, attrs}
Event_Object	{event_id, object_id, role}
Alloy Models

FOCED_Alloy_MM.als — defines the metamodel for event-object relationships

Enhanced_FOCED_Constraints.als — adds extra structural and temporal constraints

Both models can be opened in Alloy Analyzer for validation.
