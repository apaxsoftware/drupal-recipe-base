## APAX Base Drupal Recipe

This is a Drupal 10 recipe with common modules and configuration for new projects.

This [Drupal recipe](https://www.drupal.org/docs/extending-drupal/drupal-recipes) is designed to:

- Install certain parts of Standard install profile that we want
- Disable core modules we don't want
- Set specific contributed module configuration
- Provide a starting point for Drupal ready to develop features for without
  wasting too much time on the post-install ceremony.

## Usage

```shell
composer require apax/recipe_apax_base
drush recipe ./path/to/recipe_apax_base
```

## Local Development

This project uses Lando for local development. Starting Lando from inside this project will build
and install a containerized Drupal site with this recipe applied. You can start Lando with the
following command:

```shell
lando start
```

Reinstall the site and reapply the recipe with the following command:

```shell
lando rebuild
```
