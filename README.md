# iRCX Paper Artifacts

Routed DEF benchmarks and the capacitance lookup table used in the evaluated iRCX
paper-data configuration.

## Contents

- `captab/out.captab`: the archived iRCX capacitance lookup table.
- `def/`: ten routed benchmark designs generated using ecc-tools iRT.
- `benchmarks.txt`: benchmark names in the order used in the paper.
- `metadata.json`: identifiers for the evaluated extractor and capacitance table.
- `SHA256SUMS`: checksums for the capacitance table and DEF files.

The benchmarks are s713, s1238, s1488, s5378, s9234, s13207, s15850, s35932,
s38417, and s38584. They use the same 28 nm technology configuration.

## Verify the Files

From the repository root:

```bash
sha256sum -c SHA256SUMS
```

The capacitance table and all DEF files are byte-identical to the preserved
paper-data inputs. Their original numerical values and routing geometry have
not been modified for packaging.

## Use with iRCX

Use `captab/out.captab` as the iRCX capacitance-table input and the corresponding
`def/<benchmark>.def` as the routed design input. The extractor must also be given
the matching technology LEF, cell LEFs, process description, and layer mapping.

This repository contains input data only. Extractor source, technology libraries,
commercial-reference SPEFs, comparison reports, and the complete experiment runner
are separate. The files here alone do not reproduce the full paper evaluation.

The source identifiers in `metadata.json` describe the evaluated snapshots in the
authors' experiment archive; they do not assert that those snapshots are already
available in a public source repository.
