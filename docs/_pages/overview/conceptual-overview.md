---
layout: default
title: Conceptual Overview
permalink: /conceptual-overview/
---

# Conceptual Overview

## The Free Energy Principle

The Free Energy Principle (FEP), developed by neuroscientist Karl Friston, proposes that biological systems work to minimize their variational free energy - essentially minimizing the difference between their internal model of the world and their sensory inputs.

## Beyond Reactive AI

Traditional game AI is often reactive and rule-based. NPCs follow predefined scripts or decision trees that determine their behavior based on current conditions.

FAITH aims to address these limitations by giving NPCs:

- **Memory**: Tracking past events and their outcomes
- **Prediction**: Anticipating player actions and world changes
- **Adaptation**: Updating internal models based on experience

## System Architecture

The FAITH architecture consists of several interconnected models:

- [Perception Model](/perception-model/): How agents sense and process the game world
- [Belief Model](/belief-model/): How agents form and update internal world models
- [Action Model](/action-model/): How agents decide what actions to take

<div class="mermaid">
flowchart TB
    %% Main system components with clear subgraphs
    subgraph Agent["Game Agent"]
        direction TB
        AgentCore["Agent Core"]
    end

    subgraph PerceptionModel["Perception Model"]
        direction TB
        
        subgraph PerceptionSystems["Perception Systems"]
            direction LR
            Vision["Vision System"]
            Proprio["Proprioception System"]
        end
        
        subgraph MotorControl["Motor Control"]
            direction LR
            NavControl["Navigation Controller"]
            Anim["Animator"]
        end
        
        subgraph Sensors["Sensor Processing"]
            direction TB
            VisionCam["Vision Camera Agent"]
            ObjSerial["Object Serializer Agent"]
        end
        
        subgraph Orchestration["Orchestration Layer"]
            direction TB
            ReasonOrch["Reasoning Orchestrator"]
        end
    end
    
    subgraph BeliefModel["Belief Model"]
        direction TB
        BeliefRouter{"Belief Router"}
        
        subgraph BeliefLLMs["Belief LLM Processing"]
            direction LR
            CloudLLM_B["Cloud LLM (Complex)"]
            LocalLLM_B["Local LLM (Simple)"]
        end
        
        BeliefSystem["Agent Belief System"]
    end
    
    subgraph ActionModel["Action Model"]
        direction TB
        ActionRouter{"Action Router"}
        
        subgraph ActionLLMs["Action LLM Processing"]
            direction LR
            CloudLLM_A["Cloud LLM (Complex)"]
            LocalLLM_A["Local LLM (Simple)"]
        end
        
        ActionParser["Agent Action Parser"]
    end
    
    subgraph Execution["Execution Layer"]
        direction TB
        BehaviorTree["Behavior Tree"]
    end
    
    %% Connections between components
    Agent --> PerceptionModel
    
    %% Internal Perception Model connections
    PerceptionSystems --> Sensors
    Proprio --> MotorControl
    Sensors --> Orchestration
    MotorControl --> Orchestration
    
    %% Flow between major components
    ReasonOrch -->|"Perceived state as text"| BeliefRouter
    BeliefRouter -->|"Complex reasoning"| CloudLLM_B
    BeliefRouter -->|"Simple reasoning"| LocalLLM_B
    CloudLLM_B --> BeliefSystem
    LocalLLM_B --> BeliefSystem
    
    BeliefSystem -->|"Updated belief state"| ActionRouter
    ActionRouter -->|"Complex actions"| CloudLLM_A
    ActionRouter -->|"Simple actions"| LocalLLM_A
    CloudLLM_A --> ActionParser
    LocalLLM_A --> ActionParser
    
    ActionParser --> Execution
    Execution --> Agent
</div>

## Timeline

See the [Development Timeline](/development-timeline/) for the project schedule.
