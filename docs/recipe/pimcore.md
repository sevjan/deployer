<!-- DO NOT EDIT THIS FILE! -->
<!-- Instead edit recipe/pimcore.php -->
<!-- Then run bin/docgen -->

# How to Deploy Pimcore

[Source](/recipe/pimcore.php)

## How to deploy a Pimcore project with zero downtime?

- First, [install](/docs/installation.md) the Deployer. 
- Second, require `recipe/pimcore.php` recipe into your _deploy.php_ or _deploy.yaml_ file.
- Third, and now you can have a zero downtime deployment!

Did you know that you can deploy **Pimcore** project with a single command? Just execute `dep deploy`.
Something went wrong? Just run `dep rollback` to rollback your changes.
Also, you can take an advantage of the [Deployer's CLI](/docs/cli.md) to deploy your project.

Another feature of the Deployer is [provisioning](/docs/recipe/provision.md). Take any server, and run `dep provision` command.
This command will configure webserver, databases, php, https, and more. 
You will get everything you need to run your **Pimcore** project.

Deployer does next steps to [deploy](#deploy) **Pimcore**:
* Displays info about deployment
* Prepares host for deploy
* Locks deploy
* Prepares release
* Updates code
* Creates symlinks for shared files and dirs
* Makes writable dirs
* Installs vendors
* Clears cache
* Creates symlink to release
* Unlocks deploy
* Cleanup old releases


The pimcore recipe is based on the [symfony](/docs/recipe/symfony.md) recipe.


## Tasks

### pimcore:rebuild-classes
[Source](https://github.com/deployphp/deployer/blob/master/recipe/pimcore.php#L15)

Rebuilds Pimcore Classes.




### pimcore:custom-layouts-rebuild
[Source](https://github.com/deployphp/deployer/blob/master/recipe/pimcore.php#L20)

Creates Custom Layouts.




### pimcore:cache_clear
[Source](https://github.com/deployphp/deployer/blob/master/recipe/pimcore.php#L25)

Removes cache.




### pimcore:deploy
[Source](https://github.com/deployphp/deployer/blob/master/recipe/pimcore.php#L29)






This task is group task which contains next tasks:
* [pimcore:rebuild-classes](/docs/recipe/pimcore.md#pimcorerebuild-classes)
* [pimcore:custom-layouts-rebuild](/docs/recipe/pimcore.md#pimcorecustom-layouts-rebuild)

