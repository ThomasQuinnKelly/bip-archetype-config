# BIP Service Configuration Repository Archetype
This repository serves as an archetype from which to create new service team configuration repositories.

## Generating a Configuration Repository
After [Generating a New Project](https://github.com/department-of-veterans-affairs/bip-archetype-service#generating-a-new-project), 
follow these steps to generate a config repo for it:
1. Update `gen.properties`. Read the comments in the properties file for each property. Existing property values provide examples of how they should appear.
2. Generate the new project and read at least the last few lines of the script output. Example from the command line:

  ```bash
  $ cd ~/git/bip-archetype-config
  $ chmod +x gen.sh # optional if the script is not yet executable
  $ ./gen.sh
  ```
  
3. Move the project to the desired local git directory. For example:

  ```bash
  $ cd ~/git/bip-archetype-config
  $ mv [new-project-dir] ~/git/[new-project-dir]
  ```

4. Make an initial commit to publish to a GitHub branch. For an example of how to do this, see [git_newrepo](https://gist.github.com/c0ldlimit/4089101) - the only difference is that you may want to commit into some branch other than _master_.

## Instructions on setting up branch permissions
After creating the service team's configuration repository, follow these steps to apply branch permissions to the master branch:
1. Open your browser to your GitHub repository URL.
1. Navigate to `Settings` > `Branches`
1. Under the `Branch protection rules` section, click the `Add rule` button.
1. Set the `Branch name pattern` field's value to `master`
1. Select the following rule settings:
    * Require pull request reviews before merging
        * Required approvingg reviews: 1
        * Dismiss stale pull request approvals when new commits are pushed
    * Include administrators
    * Restrict who can push to matching branches
        * Add the `BIP ProdOps` team.
1. Click the `Create` button