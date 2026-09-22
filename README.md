# Prepared data for lisaR

Data for the RNA-seq and proteomics examples in [lisaR](https://github.com/DBM-OlmedaLab/lisaR).
The bundles contain previously computed tables, sample and design metadata,
and provenance. Downloading them does not run differential expression or
enrichment analysis.

## Examples

| Example | Data | Bundle version |
| --- | --- | --- |
| Riaz et al., GSE91061 | Paired melanoma biopsies before and during nivolumab; prepared RNA-seq results | 1.0.0 |
| CPTAC ccRCC | Paired tumour and adjacent non-tumoral tissue; prepared global-proteomic results | 1.0.0 |

The Riaz tutorial uses two DE inputs, PRE and ON, and one ON-minus-PRE LISA
profile contrast. Other saved study results are retained for reference.
CPTAC uses one paired comparison across 80 sample pairs and 6,482 genes.

## Download and use

Use a [versioned release](https://github.com/DBM-OlmedaLab/lisaR-example-data/releases).
Each includes the data archives, `MANIFEST.tsv` and `CHECKSUMS.sha256`.
The current lisaR installer knows the expected archive sizes and SHA-256 hashes:

```r
riaz <- lisaR::install_lisa_example_bundle("riaz-gse91061", "bundles/riaz")
cptac <- lisaR::install_lisa_example_bundle("cptac-ccrcc", "bundles/cptac")
```

Each call verifies and unpacks a bundle, then returns a separate project
preparation command. Follow the [Riaz](https://olmedalab.org/lisaR/reader/riaz-gse91061-worked-example.html?lang=en)
or [CPTAC](https://olmedalab.org/lisaR/reader/cptac-ccrcc-proteomics.html?lang=en)
guide for preparation and analysis. Update lisaR if it still points to the previous distribution repository.

The inner manifests cover the individual data files. Versioned assets are
immutable: a change to a bundle receives a new version and checksum. This
repository distributes data, not a second implementation of lisaR.

## Sources and attribution

- Riaz N, Havel JJ, Makarov V, et al. *Tumor and Microenvironment Evolution
  during Immunotherapy with Nivolumab*. Cell 2017;171:934-949.
  https://doi.org/10.1016/j.cell.2017.09.028. Source: GEO GSE91061.
- Clark DJ, Dhanasekaran SM, Petralia F, et al. *Integrated Proteogenomic
  Characterization of Clear Cell Renal Cell Carcinoma*. Cell 2019;179:964-983.
  https://doi.org/10.1016/j.cell.2019.10.007. Source: CPTAC ccRCC, PDC000127.
  The prepared protein-level result is not interchangeable with the PDC
  gene-level supplementary matrix.

Cite the original study and lisaR when using these data. The bundle notices
record the source, derivation and applicable data-use conditions. The software
licence of lisaR does not grant additional rights over the underlying research
data. These bundles contain no raw sequencing reads, original full proteomic
matrix, MSigDB memberships or KEGG maps.
