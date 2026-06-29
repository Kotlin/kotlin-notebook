[![Marketplace version](https://img.shields.io/jetbrains/plugin/v/16340-kotlin-for-jupyter?color=green&label=Latest%20version)][Marketplace]
[![Marketplace downloads](https://img.shields.io/jetbrains/plugin/d/16340?label=Downloads)][Marketplace]
[![Apache 2.0 License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

# Kotlin Notebook

<!-- Plugin description -->
Kotlin support for running and editing Jupyter notebooks in IntelliJ IDEA
<!-- Plugin description end -->

The **Kotlin Notebook** plugin is an IntelliJ IDEA plugin that enables you to create and edit
[Kotlin notebooks](https://www.jetbrains.com/help/idea/kotlin-notebook.html) directly within the IDE.
It acts as a client for the [Kotlin Jupyter kernel](https://github.com/Kotlin/kotlin-jupyter).

## Repository status

Starting from IntelliJ IDEA 2026.2, JetBrains sunsetted Kotlin Notebook as a
product and will no longer maintain or support the plugin. The plugin remains
available under an open-source model so the community can continue its
development. More details in the [blog post](https://blog.jetbrains.com/idea/2026/06/kotlin-notebook-sunset).

The source in this repository reflects the latest state of the plugin. However, for technical
reasons, the repository is not fully self-contained right now: building the plugin and running
the tests may not work out of the box after cloning. We're working on making this a fully
buildable, runnable project. It will take some time, and this README will be updated once
that's done.

## Features

- Syntax highlighting, inlay hints, inspections, find usages, and refactorings in notebook cells
- Rich output rendering (HTML, images, Swing components, plots)
- Interactive debugger support for notebook cells
- Library integrations via `%use` magic and `@file:DependsOn()`
- Gradle / Maven project integration
- Tables, DataFrames, and Let's Plot visualisation

For full documentation see:
- [Kotlin Notebook overview](https://kotlinlang.org/docs/kotlin-notebook-overview.html)
- [IntelliJ IDEA help](https://www.jetbrains.com/help/idea/kotlin-notebook.html)

## Plugin structure

The plugin is built as a multi-module Gradle project. Each content module corresponds to a
feature area and is packaged as a separate JAR inside the plugin distribution:

| Module | Description |
|--------|-------------|
| `core` | Core notebook editor, REPL connectivity, file-type support |
| `k1` | K1 (classic frontend) specific analysis |
| `k2` | K2 (FIR frontend) specific analysis |
| `debug` | Debugger integration |
| `debug:renders` | Custom debugger renderers |
| `plots` | Let's Plot visualisation support |
| `tables` | DataFrame / table rendering |
| `sql` | SQL language injection in cells |
| `export:pdf` | PDF export |
| `buildSystems:gradle` | Gradle project integration |
| `liveTemplates` | Kotlin Notebook live templates |
| `notekit` | Notekit API support |
| `performancePlugin` | Performance testing commands |

## Building

### Prerequisites

- JDK 21
- Git

### Build from source

```sh
./gradlew build
```

### Run the plugin in a sandboxed IDE

```sh
./gradlew runIde
```

### Run tests

```sh
./gradlew test
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

This project is licensed under the [Apache License 2.0](LICENSE).

[Marketplace]: https://plugins.jetbrains.com/plugin/16340-kotlin-for-jupyter
