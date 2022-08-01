# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [unreleased]

### Added

- Example in README
- Step names

_Nothing as of yet_

## [v1.0.0] - 2022-07-31

### Added

- First version of the action
  - Grabs the Data Dragon versions index and picks the first patch number via regex
  - Patch number is saved in an output variable for further usage
  - Will fail if Data Dragon can't be reached or if patch number seems invalid
- Changelog
- Readme
- MIT License

[//]: # 'Links to releases:'
[unreleased]: https://github.com/marvinscham/get-league-patch/compare/v1.0.0...main
[v1.1.0]: https://github.com/marvinscham/get-league-patch/compare/v1.0.0...v1.1.0
[v1.0.0]: https://github.com/marvinscham/get-league-patch/commits/v1.0.0
