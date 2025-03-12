---
layout: default
title: Core Library
permalink: /core-library/
---

# Core Library

The FAITH Core Library is the engine-agnostic foundation of the architecture, providing the fundamental AI systems that power agent behavior.

## Overview

The Core Library implements the theoretical foundations of Active Inference and the Free Energy Principle in a modular, extensible framework. It's designed to be independent of any specific game engine or application, focusing purely on the cognitive processes that drive agent behavior.

## Key Components

### Perception System

The Perception System processes and structures incoming sensory data:

- **Sensory Input Processor**: Normalizes and filters raw sensory data
- **World Serializer**: Converts game-specific object representations into a standardized format
- **Short-term Memory**: Maintains a buffer of recent perceptions for temporal reasoning

[Learn more about the Perception Model](perception-model.html)

### Generative Model

The Generative Model maintains the agent's beliefs about the world:

- **Probabilistic World Model**: Represents the agent's understanding of the environment
- **Prediction Engine**: Generates expectations about future states
- **Uncertainty Estimator**: Quantifies confidence in beliefs and predictions

[Learn more about the Belief Model](belief-model.html)

### Belief Updater

The Belief Updater implements Bayesian inference to refine the agent's world model:

- **Bayesian Inference Engine**: Updates beliefs based on new evidence
- **Prediction Error Calculator**: Computes the difference between predictions and observations
- **Belief Integration System**: Merges updated beliefs into the overall world model

### Policy Selector

The Policy Selector determines the optimal actions to take:

- **Action Evaluator**: Assesses potential actions against current goals
- **Expected Free Energy Calculator**: Computes EFE to minimize surprise
- **Action Prioritizer**: Ranks actions based on expected outcomes

[Learn more about the Action Model](action-model.html)

### LLM Orchestration

The LLM Orchestration system manages interactions with language models:

- **Reasoning Router**: Determines when to use local vs. cloud processing
- **Context-Aware Prompt Generator**: Creates effective prompts based on current context
- **Response Parser & Integrator**: Interprets LLM outputs and integrates them into the belief system

### Core Systems

Supporting infrastructure for the cognitive components:

- **Configuration System**: Manages agent parameters and runtime settings
- **Logging & Diagnostics**: Records agent state and decision processes
- **Performance Profiling**: Monitors and optimizes computational resource usage

## Implementation Approach

The Core Library will be implemented in modern C++ with these considerations:

- **Performance-Critical Components**: Optimized for real-time performance in game environments
- **Modularity**: Clear interfaces between components to allow selective replacement
- **Minimal Dependencies**: Limited external dependencies to maximize portability
- **Thread Safety**: Designed for concurrent operation where appropriate
- **Memory Efficiency**: Careful memory management for game environments

## Integration Points

The Core Library connects to the rest of the FAITH architecture through:

- [Engine Bindings](engine-bindings.html): Adapters for specific game engines
- [Game-Specific Systems](game-specific-systems.html): Customizations for particular games
