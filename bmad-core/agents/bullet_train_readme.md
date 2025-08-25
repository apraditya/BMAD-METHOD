# Bullet Train Agent for BMad Method

This agent helps developers work with the Bullet Train framework following its conventions and patterns, including Avo admin panel integration.

## Overview

Bullet Train is a Ruby on Rails framework that provides a solid foundation for SaaS applications with built-in team-based multi-tenancy, authentication, and admin panels. This project also integrates Avo, a powerful admin panel solution for Rails applications.

## Key Bullet Train Principles

1. **Team-Centric Architecture**: All data is scoped to teams via `team_id`
2. **Personal Teams**: Each user automatically gets a personal team upon signup
3. **Role-Based Access Control**: Users belong to teams via `TeamMembership` with roles
4. **UUID Primary Keys**: All tables use UUIDs instead of integers for better security
5. **Scoped Uniqueness**: All validations include `scope: :team_id`
6. **Super Scaffolding**: Automated code generation for consistent CRUD operations
7. **Avo Admin Panel**: Integration with Avo for admin data management

## Key Avo Concepts

1. **Resources**: Avo resources map to Rails models for admin management
2. **Fields**: Configure how model attributes appear in the admin panel
3. **Associations**: Manage relationships between models in the admin panel
4. **Search**: Implement search functionality for resources
5. **Filters**: Add filtering capabilities to resource views
6. **Actions**: Create custom actions for bulk operations or workflows

## Avo Feature Levels

- **Standard**: Basic CRUD operations, standard field types, associations
- **Pro** (Paid): Advanced field types (rich text, file uploads), custom views, API integration
- **Advanced** (Paid): Role-based access control, multi-tenancy support, advanced reporting

Note: Some features referenced in templates may require Avo Pro or Advanced licenses.

## Using the Agent

To activate the Bullet Train Developer agent, type:

```
*bt-dev
```

The agent will guide you through implementing features that follow Bullet Train conventions, including creating Avo resources for admin panel management.

## Components

- `bullet_train_developer.md`: The agent definition
- `implement-bt-feature.yaml`: Task template for implementing features
- `bullet-train-conventions.yaml`: Checklist for verifying conventions
- `bullet-train-model.md`: Template for creating models
- `avo-resource.md`: Template for creating Avo resources
- `create-avo-resource.yaml`: Task template for creating Avo resources

## Best Practices

1. Always scope models to teams using the Bullet Train concerns
2. Use Super Scaffolding for generating standard CRUD operations
3. Keep controllers skinny and business logic in models or service objects
4. Ensure all queries are automatically filtered by the current team context
5. Validate all uniqueness constraints with `scope: :team_id`
6. Create Avo resources for all models that need admin management
7. Configure appropriate fields in Avo resources for effective admin management