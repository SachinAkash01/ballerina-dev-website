---
layout: ballerina-left-nav-release-notes
title: Swan Lake Update 9 (2201.9.2) 
permalink: /downloads/swan-lake-release-notes/2201.9.2/
active: 2201.9.2
---

## Overview of Ballerina Swan Lake Update 9 (2201.9.2)

<em>Swan Lake Update 9 (2201.9.2) is the second patch release of Ballerina 2201.9.0 (Swan Lake Update 9) and it includes a new set of bug fixes to the language server, runtime, library and developer tooling.</em>

## Update Ballerina

Run the command below to update your current Ballerina installation directly to 2201.9.2 by using the [Ballerina Update Tool](/learn/update-tool/).

```
$ bal dist pull 2201.9.2
```

## Install Ballerina

If you have not installed Ballerina, then, download the [installers](/downloads/#swanlake) to install.

<!-- ADD ONLY THE APPLICABLE SECTIONS FROM THE BELOW -->

## Language updates

### Bug fixes

To view bug fixes, see the [GitHub milestone for Swan Lake Update 9 (2201.9.2)](https://github.com/ballerina-platform/ballerina-lang/issues?q=is%3Aissue+label%3AType%2FBug+is%3Aclosed+milestone%3A2201.9.2).

## Runtime updates

### Bug fixes

To view bug fixes, see the [GitHub milestone for Swan Lake Update 9 (2201.9.2)](https://github.com/ballerina-platform/ballerina-lang/issues?q=is%3Aissue+milestone%3A2201.9.2+label%3ATeam%2FjBallerina+label%3AType%2FBug+is%3Aclosed).

## Ballerina library updates

### Bug fixes

To view bug fixes, see the [GitHub milestone for Swan Lake Update 9 (2201.9.2)](https://github.com/ballerina-platform/ballerina-library/issues?q=is%3Aissue+label%3AType%2FBug+is%3Aclosed+milestone%3A2201.9.2).

## Developer tools updates

### New features

#### WSDL tool

Introduced the WSDL CLI tool as an experimental feature that generates Ballerina types from a WSDL file. This tool can be accessed by pulling it from the Ballerina Central and running it with an input WSDL file.

Execute the following command to pull the tool from the Ballerina Central.

```
$ bal tool pull wsdl
```

Execute the following command to generate Ballerina types from a WSDL file.

```
$ bal wsdl -i <FILE_NAME> [--operations <COMMA_SEPARATED_OPERATION_NAMES>]

# -i, --input <FILE_NAME>
#     Input WSDL file from which to generate Ballerina types.

# --operations <COMMA_SEPARATED_OPERATION_NAMES>
#     Optional. Specify the list of operations, for which Ballerina types need to be generated.
```

### Bug fixes

To view bug fixes, see the GitHub milestone for Swan Lake Update 9 (2201.9.2) of the repositories below.

- [Language server](https://github.com/ballerina-platform/ballerina-lang/issues?q=is%3Aissue+label%3ATeam%2FLanguageServer+milestone%3A2201.9.2+is%3Aclosed+label%3AType%2FBug+)
- [OpenAPI](https://github.com/ballerina-platform/ballerina-library/issues?q=label%3Amodule%2Fopenapi-tools+milestone%3A2201.9.2+is%3Aclosed)
- [Bindgen tool](https://github.com/ballerina-platform/ballerina-lang/issues?q=is%3Aissue+label%3AArea%2FBindgen+milestone%3A2201.9.2+is%3Aclosed)
- [CLI](https://github.com/ballerina-platform/ballerina-lang/issues?q=is%3Aissue+milestone%3A2201.9.2+is%3Aclosed+label%3AType%2FBug+label%3AArea%2FCLI-BuildTools)

## Ballerina packages updates

### Improvements

Introduced an experimental build option to enable memory-efficient compilation of package dependencies. This can help prevent out-of-memory issues during the initial compilation with a clean central cache. Pass the flag to the `bal` command or specify the build option in the `Ballerina.toml` file to enable this experimental feature.

```
$ bal build --optimize-dependency-compilation
```

Specifying the build option in the `Ballerina.toml` file:

```toml
[build-options]
optimizeDependencyCompilation = true
```
