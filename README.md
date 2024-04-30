# Installers for Helios++

This project creates installer scripts and executables for [Helios++](https://github.com/3dgeo-heidelberg/helios).

## How to create installers

The installers are created by [constructor](https://github.com/conda/constructor). The configuration
for `constructor` is located in `construct.yaml.j2` - where the Jinja2 syntax is resolved in the
GitHub Actions CI.

When you applied changes to the configuration, you can create a new installer
by manually triggering the workflow `installer.yml`. The version of Helios++
for which you are creating the installer can be passed as a workflow input.

The installers are uploaded as artifacts in GitHub Actions.

## Menu items

The installers do not only install Helios++, but also menu items to use them.
These are installed in a separate conda package: [helios-menuinst](https://anaconda.org/conda-forge/helios-menuinst).
The sources for this package are located directly in the [helios-menuinst-feedstock](https://github.com/conda-forge/helios-menuinst-feedstock).
The [menuinst](https://github.com/conda/menuinst) config is located in `recipe/src/menu.json`.

## Known issues

* Uninstallations triggered through the App Settings in Windows do (sometimes?) throw errors.
  Manually running the uninstaller from the installation prefix works very good though.
