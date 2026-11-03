# PM4Py

[![PyPI version](https://img.shields.io/pypi/v/pm4py.svg)](https://pypi.org/project/pm4py/)
[![Python versions](https://img.shields.io/pypi/pyversions/pm4py.svg)](https://pypi.org/project/pm4py/)
[![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](LICENSE)
[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.simpa.2023.100556-blue.svg)](https://doi.org/10.1016/j.simpa.2023.100556)

PM4Py is a Python library providing state-of-the-art algorithms and tools for process mining.

It is developed and maintained by [Process Intelligence Solutions GmbH (PIS)](https://processintelligence.solutions/).

## Getting started

Installation instructions, tutorials, and the full documentation are maintained on the PM4Py website:

- [Installation guide](https://processintelligence.solutions/pm4py/installation)
- [Tutorials and examples](https://processintelligence.solutions/pm4py/examples)
- [Feature overview](https://processintelligence.solutions/pm4py/features)
- [API documentation](https://processintelligence.solutions/pm4py/)

## License

The open-source version of PM4Py, available on [GitHub](https://github.com/process-intelligence-solutions/pm4py), is
licensed under the [GNU Affero General Public License v3.0 (AGPL-3.0)](LICENSE).

A separate version of PM4Py is available for **commercial use in closed-source environments** under a different
license. See [PM4Py Licensing](https://processintelligence.solutions/pm4py#licensing) for details.

## Optional dependencies

The default installation covers mainstream usage. Additional integrations are grouped by feature in `pyproject.toml`:

| Extra           | Installs                                      |
|-----------------|-----------------------------------------------|
| `calendars`     | workalendar                                   |
| `connectors`    | requests                                      |
| `llm`           | openai, requests                              |
| `ml`            | pyemd, scikit-learn                           |
| `ocel`          | jsonschema, pyarrow                           |
| `polars`        | polars (dataframe support)                    |
| `solvers`       | cvxopt                                        |
| `visualization` | pyvis                                         |
| `windows`       | pygetwindow, pynput, pywin32 (Windows only)   |

The `stable` extra pins the exact dependency versions validated by the project and used in CI.

### Polars

Polars 1.40.1 and 2.x are supported. Joins used in filtering and enrichment preserve event order, including when lazy
queries run on the streaming engine (the default in Polars 2.0).

### PuLP

SciPy is the default LP solver; PuLP is optional. If PuLP is installed, PM4Py selects the matching backend for
PuLP 3.x or 4.x. PuLP 4 requires CBC to be installed separately, either with `python -m pip install "pulp[cbc]"` or by
putting `cbc` on your `PATH`.

## Release notes

See [CHANGELOG.md](CHANGELOG.md) for incremental updates.

## Contributing

Before contributing, please review the
[contributing guidelines and Contributor License Agreement (CLA)](https://processintelligence.solutions/pm4py/contributing).

For a source checkout, install the project with `python -m pip install -e .`. Build, CI, and lint dependencies are
standard dependency groups and can be installed with, for example, `python -m pip install --group lint`
(requires pip 25.1 or later).

## Third-party dependencies

As a scientific library in the Python ecosystem, PM4Py relies on external libraries. The licenses of all direct
dependencies are in the [`third_party/`](third_party/) folder, and
[`third_party/LICENSES_TRANSITIVE`](third_party/LICENSES_TRANSITIVE) lists every transitive dependency with its license.

## Citing PM4Py

If you use PM4Py in your scientific work, please cite:

> Alessandro Berti, Sebastiaan van Zelst, and Daniel Schuster (2023). PM4Py: A process mining library for Python.
> *Software Impacts*, 17, 100556. https://doi.org/10.1016/j.simpa.2023.100556

[DOI](https://doi.org/10.1016/j.simpa.2023.100556) | [Article](https://www.sciencedirect.com/science/article/pii/S2665963823000933)

BibTeX:

```bibtex
@article{pm4py,
  title   = {{PM4Py}: A process mining library for {Python}},
  author  = {Berti, Alessandro and van Zelst, Sebastiaan and Schuster, Daniel},
  journal = {Software Impacts},
  volume  = {17},
  pages   = {100556},
  year    = {2023},
  issn    = {2665-9638},
  doi     = {10.1016/j.simpa.2023.100556},
  url     = {https://www.sciencedirect.com/science/article/pii/S2665963823000933}
}
```

## Legal notice

This repository is managed by Process Intelligence Solutions GmbH. Further information about PIS is available at
[processintelligence.solutions](https://processintelligence.solutions).
