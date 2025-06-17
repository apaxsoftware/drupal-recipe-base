## APAX Base Recipe

This recipe is designed to do the following:

- Install certain parts of Standard install profile that we want
- Disable core modules we don't want
- Set specific contributed module configuration
- Provide a starting point for Drupal ready to develop features for without
  wasting too much time on the post-install ceremony.

## Drupal Recipe Initiative

Here's a link to the [Drupal Recipe Documentation and Initiative](https://www.drupal.org/project/distributions_recipes) page.

And here's a link to the multiple conributed recipes in Drupal's [Recipe Cookbook](https://www.drupal.org/docs/extending-drupal/contributed-modules/contributed-module-documentation/distributions-and-recipes-initiative/recipes-cookbook)

## Bitbucket Pipelines

This is an APAX specific portion of the README but it is important that you enable Bitbucket Pipelines and add the shared APAX Lando SSH Key to this repo (and the other recipe repos) in order to allow composer to access this private repository.

1. Toggle on Bitbucket Pipelines for the repository in Repository Settings.
1. Add SSH Key in Repository settings.
1. Open 1Password and search for the shared key named "Apax Lando SSH Key"
1. Add both the public and private keys from that 1Password entry into the repo.
1. Save.

## Naming

The repo names should likely follow the pattern of `recipe-[descriptive-name]`.

That `descriptive-name` should carry over to the composer.json file and become the name there for use later. `apax/[descriptive-name]` is how user's wishing to access this repo will use composer to require the project.

## Installing

- Start with a Drupal 10 site. (IMPORTANT)
- Install the 'Minimal' profile.
- Apply the recipe

The recipe can be applied with PHP in Drupal 10.3+.

Execute this command from the web root:

```shell
lando php web/core/scripts/drupal recipe web/recipes/contrib/[repo-name] -v
```

If all goes well, you should see the following output:

```shell
 [OK] Drupal Base applied successfully
```

Clear the cache after the recipe is applied. When going back to the site,
all the recipe configuration and customization has been applied.

## Building Recipes

Here's the Drupal guide to [building recipes](https://project.pages.drupalcode.org/distributions_recipes/recipe_author_guide.html).

## Local Development

This project uses Lando for local development. Starting Lando will install containerized Drupal site with the recipe
applied. You can start Lando with the following command:

```shell
lando start
```

Reinstall the site and reapply the recipe with the following command:

```shell
lando rebuild
```
