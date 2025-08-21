# Bullet Train Agent for BMad Method

This agent helps developers work with the Bullet Train framework following its conventions and patterns.

## Overview

Bullet Train is a Ruby on Rails framework that provides a solid foundation for SaaS applications with built-in team-based multi-tenancy, authentication, and admin panels.

## Key Bullet Train Principles

1. **Team-Centric Architecture**: All data is scoped to teams via `team_id`
2. **Personal Teams**: Each user automatically gets a personal team upon signup
3. **Role-Based Access Control**: Users belong to teams via `TeamMembership` with roles
4. **UUID Primary Keys**: All tables use UUIDs instead of integers for better security
5. **Scoped Uniqueness**: All validations include `scope: :team_id`
6. **Super Scaffolding**: Automated code generation for consistent CRUD operations

## Using the Agent

To activate the Bullet Train Developer agent, type:

```
*bt-dev
```

The agent will guide you through implementing features that follow Bullet Train conventions.

## Components

- `bullet_train_developer.md`: The agent definition
- `implement-bt-feature.yaml`: Task template for implementing features
- `bullet-train-conventions.yaml`: Checklist for verifying conventions
- `bullet-train-model.md`: Template for creating models

## Best Practices

1. Always scope models to teams using the Bullet Train concerns
2. Use Super Scaffolding for generating standard CRUD operations
3. Keep controllers skinny and business logic in models or service objects
4. Ensure all queries are automatically filtered by the current team context
5. Validate all uniqueness constraints with `scope: :team_id`