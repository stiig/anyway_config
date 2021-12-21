## Plan
1. Add parameter `current_environment` to Anyway::Settings class. Provide default value for this, maybe ENV["RAILS_ENV"]?
2. Change method Anyway::Loaders::YAML.call. Add method `environmental?` and fetch all values from Anyway::Settings.current_environment config file's section. Merge default values into resulting config keys.
3. Delete files Rails::Loaders::YAML and its tests.
4. Add specs for environments in spec/loaders/yaml_spec.rb. Also add testcases for rails.
5. Extend rbs signature for required, required_attributes class methods of Anyway::Config.
6. Inside method validate_required_attributes! of Anyway::Config class check if current key has option env and this env matches Anyway::Settings.current_environment and then raise validation error when key value is missed.

### Time
Work time: 7 hours  
Delivery date: 27.12.21