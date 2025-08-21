# Bullet Train Model Template

This template helps create models that follow Bullet Train conventions.

## Model Class Template

```ruby
class {model_name} < ApplicationRecord
  # Include Bullet Train concerns
  # The base concern provides team scoping and other standard functionality
  include {model_name.pluralize.classify}::Base
  
  # Add any additional concerns
  # 🚅 add concerns above.

  # Add belongs_to associations
  # 🚅 add belongs_to associations above.

  # Add has_many associations
  # 🚅 add has_many associations above.

  # Add has_one associations
  # 🚅 add has_one associations above.

  # Add scopes
  # 🚅 add scopes above.

  # Add validations
  # Ensure all validations include scope: :team_id for team-scoped uniqueness
  # 🚅 add validations above.

  # Add callbacks
  # 🚅 add callbacks above.

  # Add delegations
  # 🚅 add delegations above.

  # Add custom methods
  # Keep business logic in models or service objects, not controllers
  # 🚅 add methods above.
end
```

## Key Bullet Train Conventions to Follow

1. **Team Scoping**: All models that store user data must be scoped to teams via `team_id`
2. **UUID Primary Keys**: Use UUIDs instead of integers for all primary keys
3. **Scoped Validations**: All uniqueness validations must include `scope: :team_id`
4. **Super Scaffolding Comments**: Use the `# 🚅 add...` comments for Super Scaffolding integration
5. **Concerns Pattern**: Include the appropriate Bullet Train concern for the model type
6. **Namespace Organization**: Models should be organized in appropriate namespaces when needed

## Migration Template

When creating migrations for Bullet Train models, follow this pattern:

```ruby
class Create{model_name.pluralize.classify} < ActiveRecord::Migration[8.0]
  def change
    create_table :{model_name.tableize}, id: :uuid do |t|
      t.references :team, null: false, foreign_key: true, type: :uuid
      # Add other fields here
      
      t.timestamps
    end
    
    # Add team-scoped index for performance
    add_index :{model_name.tableize}, [:team_id, :created_at]
    
    # Add any other indexes as needed
  end
end
```

## Controller Template

Bullet Train controllers should inherit from the appropriate base controller:

```ruby
class Account::{model_name.pluralize.classify}Controller < Account::ApplicationController
  # Use the super_load_and_authorize_resource concern for standard CRUD operations
  include SuperLoadAndAuthorizeResource
  
  # Add any custom actions here
end
```