# github-config-as-code
Configuration as code for the GitHub Platform

Overview repository for this setup. Since most of these items need to be running in a separate org, I created them on [robs-tests](https://github.com/robs-tests/).

# Automate user onboarding and repository creation
For our training org we wanted to make the following steps easier:
1. Add new users and teams to the users.yml file
1. Create a PR
1. The workflow `pull_request.yml` workflow checks if: 
   - The user file is valid yaml
   - The users is a valid GitHub handle
   - The user is already a member of the organization
1. After merging, the `user-management.yml` workflow runs and:
   - Create the team if needed
   - Add the user to the org
   - Create repository `attendee-<userhandle>`
   - Add the user to the repo
   - Add the user to the team
   - Add the team to the repo

Link to repo: [robs-tests/user-test-repo](https://github.com/robs-tests/user-test-repo)
