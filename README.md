# gp-vanilla-ruby
Vanilla Ruby/PostgreSQL development template for Gitpod.

Instructions for setting up a [`react_on_rails`](https://github.com/shakacode/react_on_rails) project has been provided. 

## Create a new Rails project using [`react_on_rails`](https://github.com/shakacode/react_on_rails)
1. Add `react_on_rails` to your gem file. Run:
    - `bundle add react_on_rails --strict`
2. Create a new rails application in the project root. The aplication name will be the name of your repository. Run this command only from the project root:
    - `rails new <APP_NAME> --database=postgresql --skip-bundle`
3. Run the `react_on_rails` generator:
    - `rails generate react_on_rails:install --ignore-warnings`


