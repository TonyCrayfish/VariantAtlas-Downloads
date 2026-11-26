# Variant Atlas for Mac

Analyze paired C. elegans sequencing reads locally, compare suppressors against a background strain, inspect variants, export Excel reports, and make chromosome plots.

**Development version 0.1 (8) is available:** [Download the Mac installer](https://github.com/TonyCrayfish/VariantAtlas-Downloads/releases/latest/download/VariantAtlas-0.1-8-AppleSilicon.dmg). Developer ID signed and notarized by Apple.

## Requirements

- Apple Silicon Mac (M1 or newer); Intel Macs are not supported by this release.
- macOS 14 Sonoma or newer. Tested locally on an M1 Pro with 16 GB memory; 16 GB or more is recommended for whole-genome analysis.
- Paired FASTQ reads (`.fastq.gz` or `.fq.gz`); assembled FASTA files are not accepted.
- Sufficient destination space: approximately four times the compressed input size plus 5 GiB. An external SSD is recommended for large datasets.

The app includes the WBcel235 reference genome, annotations, Python and analysis tools. You do not need Xcode, Homebrew, Conda or a separate genome download. Analysis works offline. Genome updates are optional downloads.

## Install

1. Download the Apple Silicon `.dmg` from [Releases](https://github.com/TonyCrayfish/VariantAtlas-Downloads/releases).
2. Open it and drag **Tony Crayfish Variant Atlas** to **Applications**.
3. Eject the disk image, then open the app from Applications. Keep macOS security protections enabled.

## Run an analysis

1. In **Analysis**, add each strain's R1/R2 files and select the background strain.
2. Use a unique analysis name containing only letters, numbers, underscores and hyphens.
3. This version supports hermaphrodite populations. Select a destination folder with adequate space, preferably on an external drive.
4. Choose Excel columns, then click **Analyze locally**. Whole-genome analysis may take many hours.
5. **Activity** shows completed stages; the lower progress bar shows progress within supported stages. Sorting may take considerable time after alignment reaches 100%.
6. Use **Stop safely**, wait for confirmation, then eject your drive. **Resume saved run…** reuses completed stages; an interrupted stage may restart. Keep files in their original locations.
7. Results retains the previous report while a new run is active. The new report loads on successful completion. Previous analyses remain in their separate folders.

Use **Results → Columns…** to select evidence fields and double-click a variant to inspect all evidence. Molecular effect predictions do not establish suppressor causality. This app analyzes small variants, not structural variants or copy-number changes.

## Support and licensing

Contact **support@tonycrayfish.com** · https://tonycrayfish.com

By Tony Crayfish Productions - Version 0.1 (8), (c) 2026 Marc Pilon, All rights reserved.
The application source repository is private. Bundled third-party tools retain their own licenses; notices and build recipes are included in the app's `Contents/Resources/Licenses` folder. Third-party source materials accompany the release separately. No sequencing data or previous analysis results are included in the download.

## Open results shared by your instructor

Unzip the results package, choose **Open completed analysis**, and select the outer analysis folder containing `reports/atlas.json`. Do not select the `reports` folder itself. This results-only package supports inspection, plotting and Excel exports without the original FASTQ or BAM files. Rerunning or resuming an analysis requires the original data and full analysis folder.

## New in 1.3

- Activity shows stage/run elapsed time, saved stage durations, available destination space and recent file changes. Setup previews required space.
- **Stop after this stage** saves the current stage before stopping. Resume from the full analysis folder.
- **Results → Add strains to this analysis…** reuses completed alignments and processes only new reads, then recalculates combined variant calls. Use a new analysis name and keep all original analysis folders/disks available. A full completed analysis is required; a viewing-only package cannot be extended. The background and reference stay fixed.
- **Gene comparison** finds genes affected across several target strains, including different alleles. Select a gene to inspect its variants; export the filtered comparison to Excel. Counts are distinct sample names, not proven independent isolates or causal suppressors.
- Double-click a variant, bookmark it, enter a note, and click **Save bookmark & note**. **Shortlist** gathers saved variants and exports evidence plus notes to Excel.
- **Export results for sharing…** produces the viewing ZIP directly, including saved notes and plot settings. Students can generate Excel reports after opening it. No original sequencing data is included.

Existing 1.0–1.2 report folders open without conversion or reanalysis. The original reports are preserved; notes live beside them in a separate file. If upgrading, safely finish or stop an analysis before replacing its running app.

## New in 1.4: genome context and plot bookmarks

**Chromosome plot** now sits directly below Analysis. Click a point and use **Bookmark / notes…** to save it and enter a note, or **View in genome browser** to see its genomic neighborhood.

The genome browser shows the focused reference allele, gene/transcript tracks, exon/UTR and CDS blocks, strand direction, and nearby-gene distances. It supports exact gene-name/WormBase-ID search, zoom, pan and alternative transcripts. The regional variant table includes candidates plus the focused allele by default; disable the filter for all calls. Double-click a row to inspect/bookmark it, or use Focus selected to navigate. No BAM files are needed.

Reference annotation hashes are checked against the report when recorded. Legacy reports without that hash display a warning; missing custom references require the matching reference pack. Gene proximity is not proof of a regulatory target, and gene-span overlap can be intronic. Consequence annotations are unchanged. The 200-track limit is explicitly shown; zoom in to reveal crowded regions.

The index is built on demand (about 56 MiB for the bundled annotation) in reports/.genome-cache, with a local-cache fallback for read-only folders. It is not included in the installer or sharing ZIP. Reports from prior versions remain readable without conversion.

## Latest development release: 0.1 (8)

This is newer than the historical 1.4 release. Development versions now use 0.1 with increasing build numbers; 1.0 is reserved for a future production release. For a durable student link, share [the latest release page](https://github.com/TonyCrayfish/VariantAtlas-Downloads/releases/latest).

- Genome browser Previous/Next buttons navigate distinct positions. **Follow chromosome-map filters** links navigation and the table to the plotted selection; it turns on when opening a point from the map. Disable it for independent browser filters.
- Chromosome plots offer minimum/maximum alternative-read percentages and minimum depth. A configurable **High alternative-read fraction** color rule is separate from the original genotype.
- Pseudogenic transcript tracks are explicitly labelled, with exon context where supported by the reference; original reported consequences are preserved.
- An offline **User guide** is available in the sidebar.
- Plot exports record evidence thresholds; plotted Excel rows include read depth and alternative-read fraction.

Existing reports and earlier saved plot settings remain compatible. No reanalysis is needed. This GitHub download is not a TestFlight upload.
