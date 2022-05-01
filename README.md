# Rails API Template

This template is meant to be a lightweight foundation for new Rails API-only applications, free of unused Rails bloatware.

### To initialize your new Rails app, follow these steps:

1. `git clone git@github.com:spenser-brinkman/rails_api_template.git` into a local directory. Take this opportunity to rename the cloned "rails_api_template" directory to the name of your new project: `mv rails_api_template {{new_app_name}})`

2. Create a new, blank project repository on GitHub.com for your app.

3. Reinitialize the git configuration for your app, so that any changes you make are not pushed to the template's repository:
  ```
  cd {{new_app_name}}
  rm -rf .git
  git init -b main
  git remote add origin https://github.com/{{your_github_username}}/{{new_app_name}}.git
  git add .
  git commit -m "Initial commit"
  git push -u origin main
  ```

### After initializing your new repo, there are a few more things to wrap up:

1. Find all instances of `CHANGE_ME_UPPER`, `CHANGE_ME_LOWER`, and `CHANGE_ME_PORT` in this repository and replace with appropriate values (app & database names, port number, etc) for your new app.

2. Run `EDITOR=vim rails edit:credentials` which will generate a `master.key` and `credentials.yml.enc` file. The `master.key` is ignored by Git, so that same `master.key` file needs to be manually added to every envrionment on which the app is installed. Rails credentials allows for encrypted storage of sensitive data like passwords and API keys used by the app's code. Access a credential in your code by calling: `Rails.application.credentials.{{credential key name}}`

3. Add any additional Gems to the Gemfile and run `bundle install`.

This template was initially generated with the following command:
`rails new rails_api_template --api -d postgresql --skip-action-mailer --skip-action-mailbox --skip-action-text --skip-active-job --skip-active-storage --skip-action-cable --skip-sprockets --skip-javascript --skip-turbolinks --skip-test --skip-system-test`
