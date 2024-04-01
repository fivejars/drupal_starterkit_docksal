This is a Docksal-based for the [FiveJars StarterKit](https://github.com/fivejars/drupal_starterkit) Drupal distribution.

[Docksal](https://docksal.io/) is used as a local development environment.

# Get Started

You need to install Docksal on your local machine according to [Docksal setup](http://docksal.readthedocs.io/en/master/getting-started/env-setup/) instructions.

## Full install from scratch

Note: a local instance of PHP and/or Composer is not required.

Follow these steps to get fully prepared project.

#### Install Docksal
```bash
curl -fsSL https://get.docksal.io | bash
```

#### Clone FiveJars StarterKit docksal project
```bash
git clone git@github.com:fivejars/drupal_starterkit_docksal.git starterkit
```

#### Add your custom settings

- Copy `example.docksal-local.env` file to `docksal-local.env` file inside `.docksal` directory.
- Use `PROJECT_VERSION` to specify the branch of the
  `fivejars/drupal_starterkit_project` to be used as a composer project. In the most
  cases you'll need:

  - `master` for a latest development version.

- Use `DISTRIBUTION_VERSION` to specify the branch of the `fivejars/drupal_starterkit` will
  be checkout automatically. Take in mind, the version corresponds the one,
  required in a root `composer.json`. Use `master` to start the development from
  the latest distribution progress.

- During an execution of a `build_project` command, all the directories except
  an ignored ones would be deleted.
  If you work on the existing project and want to save any folder in a project
  root directory - add folder name to `IGNORE_CUSTOM`. Directories names should be
  separated with spaces.

#### Build FiveJars StarterKit project
Run this command inside your project directory:
```bash
fin build_project
```
As a result you will get full FiveJars StarterKit Website installation in your file system.

The "Killed" message during command run usually means that you need to increase
memory limits in your Docksal. For macOS or Windows overall memory volume
available for Docker is limited by the virtual machine or Docker Desktop
settings.

#### Install FiveJars StarterKit website

After `fin build_project` command finish you need to install a site. For this
you can use `fin init` command.

### Start the project

```bash
fin init
```

The webserver starts up, and the site will be installed automatically with `drush si`.
