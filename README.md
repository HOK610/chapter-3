# Chapter 3: Creating an SBOM Manifest

This chapter explains how to create a software bill of materials (SBOM) manifest for analysis by Red Hat Trusted Profile Analyzer (RHTPA).

## Contents

- `Chapter-3` - AsciiDoc instructions for generating SBOM manifests
- `Chapter 30` - Additional chapter content

## Requirements

Install [Syft](https://github.com/anchore/syft) for your workstation. Red Hat's Syft Technology Preview is also available through the [Red Hat Ecosystem Catalog](https://catalog.redhat.com/en/software/containers/rh-syft-tech-preview/syft-rhel9/65b2745c19638ad4ad858412?architecture=amd64&image=661ce4dbfcbcdbfdecc6ffb8).

RHTPA supports these JSON SBOM formats:

- CycloneDX 1.3, 1.4, 1.5, and 1.6
- SPDX 2.2 and 2.3

## Examples

Create a CycloneDX SBOM from a container image:

```shell
syft registry:example.io/hello-world:latest -o cyclonedx-json@1.5
```

Create an SPDX SBOM from a container image:

```shell
syft registry:example.io/hello-world:latest -o spdx-json@2.3
```

Create an SBOM from a local directory or file:

```shell
syft dir:. -o cyclonedx-json@1.5
syft file:/example-binary -o spdx-json@2.3
```

See the [Syft documentation](https://github.com/anchore/syft) for supported image and file-system sources.

## Additional Resources

- [NTIA SBOM generation guide](https://www.ntia.gov/files/ntia/publications/howto_guide_for_sbom_generation_v1.pdf)
- [Generating SBOM documents from container images](https://github.com/guacsec/trustify/blob/main/etc/gensbom/README.md)
