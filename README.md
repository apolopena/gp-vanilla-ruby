# gp-vanilla-ruby
Vanilla Ruby/PostgreSQL development template for Gitpod.

Instructions for setting up a [`react_on_rails`](https://github.com/shakacode/react_on_rails) project has been provided below. 

## Manually create a new Rails project using [`react_on_rails`](https://github.com/shakacode/react_on_rails)
If you would like the rails README.md to be generated then rename this file before getting started: `mv README.md STARTER_README.md`

This starter project is geared toward setting up new project with rails and react using `react_on_rails`. Follow the steps below:
1. Create a new rails application in the project root. The application name will be the name of your repository. Run this command only from the project root:
    - `rails new . --database=postgresql --skip-bundle --skip-gemfile --skip --skip-webpack-install`
2. Run the `react_on_rails` generator, add the `--redux` flag if you want redux scaffolding installed:
    - `rails generate react_on_rails:install --ignore-warnings`
3. Run: `rails webpacker:install`
4. Run: `rails webpacker:install:react`
5. Bypass (for development) rails 6 blocked host functionality:
  - Open `config/environments/development.rb` and near the top of the file but inside the `Rails.application.configure do` block add these two lines:
    -  \# Clear whitelist: Disable rails 6 Blocked Host functionality
    - config.hosts.clear
6. Remove the 'loose' warning for `plugin-proposal-private-methods`
    - In `babel.config.js` add the following line to the `plugins` array:
    - `["@babel/plugin-proposal-private-methods", { "loose": true }],`
7. Create the project database. Run:
    - `rake db:create`

## Keep your `config/master.key` safe
To access rails custom [encoded credentials](https://guides.rubyonrails.org/security.html#custom-credentials), keep the key found in `config/master.key` in a safe place such as a password encryption system since this file is in the `.gitignore` and will be lost forever whenever a new workspace is created. Without the original `master.key` you will loose any secret keys that you have encrypted via the `bin/rails credentials:edit` command in `config/credentials.yml.enc`

## Run the development server
You can now development start the server with `rails -s` which will compile all assets every time there is a change or start the server with `foreman` which will compile only the changed assets and adds the option to use HMR (hot module reloading) by running: `foreman start -f Procfile.dev-hmr`

The hello_world example can be found at the route `hello_world`




