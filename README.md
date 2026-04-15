[![channel](https://img.shields.io/badge/prefix.dev%2Fsp--nightly--forge-F7CC49?style=flat-square)](https://prefix.dev/channels/sp-nightly-forge)

# (Unofficial) nightly conda packages, for the world of scientific Python.

This repository is a 'forge' which turns the source code of packages surrounding the [Scientific Python ecosystem](https://scientific-python.org/about/)
into [conda](https://conda.org/) packages which are published to [the `sp-nightly-forge` channel](https://prefix.dev/channels/sp-nightly-forge)
of https://prefix.dev/channels.

Packages can be forged from development versions of package sources on a regular basis, hence the label ['nightly'](https://scientific-python.org/specs/spec-0004/).

## Usage

Example usage with `pixi.

```console
$ pixi init example && cd example
Created /example/pixi.toml
$ pixi workspace channel add https://prefix.dev/sp-nightly-forge
Added https://prefix.dev/sp-nightly-forge
$ pixi add https://prefix.dev/sp-nightly-forge::numpy
Added https://prefix.dev/sp-nightly-forge::numpy
$ pixi list numpy
Name   Version     Build            Size  Kind   Source
numpy  2.5.0.dev0  hb0f4dca_0  30.11 MiB  conda  https://prefix.dev/sp-nightly-forge
```

## Implementation details

The forge is implemented around the [`pixi publish`](https://pixi.prefix.dev/latest/reference/cli/pixi/publish/) command.
[The Forge workflow](https://github.com/lucascolley/sp-nightly-forge/blob/main/.github/workflows/forge.yml) specifies the packages to be built
and invokes `pixi publish`.
Packages are forged from [Pixi package](https://pixi.prefix.dev/latest/reference/pixi_manifest/#the-package-section) definitions, which can live
either in a remote repository, or in [the `packages` directory of the forge](https://github.com/lucascolley/sp-nightly-forge/tree/main/packages).
>>>>>>> dc8e66a (add README)
