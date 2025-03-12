---
layout: custom_default
title: Engine Bindings
---

# Engine Bindings

The Engine Bindings layer connects the FAITH Core Library to specific game engines, providing the necessary integration points for seamless operation.

## Overview

Game engines have different architectures, object models, and programming interfaces. The Engine Bindings layer abstracts these differences, allowing the core FAITH systems to operate consistently regardless of the underlying engine.

## Abstract Integration Layer

The Abstract Integration Layer defines common interfaces for engine-specific implementations:

- **Perception Adapters**: Convert engine-specific scene representations to FAITH's internal format
- **Action Executors**: Translate FAITH action decisions into engine-specific commands
- **Resource Management**: Handle engine-specific memory and performance considerations
- **Threading Model**: Adapt to each engine's concurrency patterns

## Game Engine Implementations

### Godot Extension

The Godot implementation provides integration with the open-source Godot Engine:

- GDExtension-based integration
- Node-based architecture mapping
- Signal system integration for event handling
- Support for both 2D and 3D environments

### Unreal Plugin

The Unreal implementation offers integration with Unreal Engine:

- UE Plugin architecture
- Actor Component design for easy attachment to game objects
- Blueprint support for designer-friendly configuration
- Integration with Unreal's AI subsystems

### Unity Package

The Unity implementation delivers integration with Unity Engine:

- Unity Package Manager distribution
- MonoBehaviour-based components
- Integration with Unity's animation and navigation systems
- Support for DOTS/ECS architecture (optional)

## Development Tools

The Engine Bindings layer also includes development tools to aid in debugging and tuning:

- **State Visualizer**: Graphical representation of agent beliefs and decision processes
- **Belief Debugger**: Interactive tool for inspecting and modifying agent beliefs
- **Performance Analyzer**: Profiling tools for optimizing agent performance

## Implementation Considerations

- **Engine Version Support**: Clear documentation of supported engine versions
- **Minimal Overhead**: Efficient bridging with minimal performance impact
- **Non-Invasive Integration**: Design that doesn't require extensive modifications to existing game code
- **Graceful Degradation**: Fallback mechanisms when engine features are unavailable

## Getting Started

Each engine binding includes:

- Installation instructions
- Basic setup guide
- Example scenes/levels
- API documentation

## Integration with Game-Specific Systems

The Engine Bindings layer connects to:

- [Core Library](core-library.html): The engine-agnostic AI systems
- [Game-Specific Systems](game-specific-systems.html): Customizations for particular games
