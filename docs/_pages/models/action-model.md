---
layout: default
title: Action Model
permalink: /action-model/
---

# Action Model

The Action Model determines how FAITH agents decide what actions to take based on their beliefs.

## Overview

The action system translates the agent's beliefs and goals into concrete actions in the game world. It implements the "active" part of active inference, where agents act to confirm their predictions and minimize surprise.

## Components

### Action Router

Similar to the Belief Router, the Action Router determines the appropriate processing level for action decisions:

- Routine actions use efficient local processing
- Complex planning leverages more powerful cloud-based reasoning

### Action LLM Processing

Two tiers of language models support action selection:

- **Local LLM**: Handles common action decisions with minimal latency
- **Cloud LLM**: Provides strategic planning and complex decision-making

### Agent Action Parser

Translates high-level action decisions into specific game commands that can be executed by the Behavior Tree.

## Policy Selection

The Action Model implements policy selection based on:

- Expected free energy minimization
- Goal-directed behavior
- Risk assessment and uncertainty handling
- Resource management (energy, time, etc.)

## Execution Layer

The Behavior Tree serves as the final execution layer, translating high-level action decisions into specific game animations and mechanics.

## Implementation Considerations

- Balancing reactivity with deliberative planning
- Graceful fallback when cloud services are unavailable
- Configurable action capabilities for different agent types
- Integration with game-specific action systems
