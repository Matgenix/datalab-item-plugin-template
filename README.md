# datalab-item-plugin-template

> [!WARNING]
> This repository is still under active development and will have some rough edges.
Please raise any issues in the [Issue Tracker](https://github.com/datalab-org/datalab-item-plugin-template/issues?q=sort%3Aupdated-desc+is%3Aissue+is%3Aopen) or contact us via the routes listed at [datalab-org](https://github.com/datalab-org).

A [Copier](https://github.com/copier-org/copier) template for [*datalab*](https://datalab-org.io) plugins that register **custom item types** via the `pydatalab.item_types` entry point (the sibling of [datalab-app-plugin-template](https://github.com/datalab-org/datalab-app-plugin-template), which targets *block* plugins).

> [!IMPORTANT]
> Custom item types are not yet part of a released *datalab* version; generated
> plugins currently develop against the `ml-evs/custom-items` branch of
> [datalab-org/datalab](https://github.com/datalab-org/datalab) (wired up in the
> generated `pyproject.toml` via `[tool.uv.sources]`).

The generated plugin contains a documented example item model demonstrating the
`datalab_*` schema annotations (references to other items, values with units,
enums, multi-line text, field sections, summary projection, ...). By default the
*datalab* web UI renders these fields automatically from their annotations — no
JavaScript required. Answer *yes* to the `include_custom_panel` question to also
scaffold a custom Vue panel (`webapp/<ClassName>Panel.vue`), which takes over
rendering of all the item's custom fields and is bundled into the webapp with
`invoke dev.collect-plugin-panels`.

We recommend using `uv` to manage Python versions and environments, in which case the template can be used with:

```shell
uvx copier copy "git@github.com:datalab-org/datalab-item-plugin-template" <my_plugin>
```

This will guide you through the process of creating a new repository for your plugin.
You can commit the result, alongside the `.copier-answers.yml` file, to your new repository (after creating it on GitHub or elsewhere):

```shell
cd <my_plugin>
git init
git add .
git commit -m "Initial commit"
git remote add origin <your-repo-url>
```

You can also occasionally sync changes from this template by running the following command in your plugin repository:

```shell
uvx copier update
```

Releases of the plugin are created via semantic version tags on GitHub.
