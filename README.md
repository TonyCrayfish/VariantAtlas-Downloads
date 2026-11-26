# Variant Atlas for Mac

Analyze paired C. elegans sequencing reads locally, compare suppressors against a background strain, inspect variants, export Excel reports, and make chromosome plots.

**Download status:** Version 1.2 is being prepared. The public download will appear here after Apple notarization completes.

## Requirements

- Apple Silicon Mac (M1 or newer); Intel Macs are not supported by this release.
- macOS 14 Sonoma or newer. Tested locally on an M1 Pro with 16 GB memory; 16 GB or more is recommended for whole-genome analysis.
- Paired FASTQ reads (`.fastq.gz` or `.fq.gz`); assembled FASTA files are not accepted.
- Sufficient destination space: approximately four times the compressed input size plus 5 GiB. An external SSD is recommended for large datasets.

The app includes the WBcel235 reference genome, annotations, Python and analysis tools. You do not need Xcode, Homebrew, Conda or a separate genome download. Analysis works offline. Genome updates are optional downloads.

## Install (when the release is available)

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

By Tony Crayfish Productions - Version 1.2, (c) 2026 Marc Pilon, All rights reserved.
The application source repository is private. Bundled third-party tools retain their own licenses; notices and build recipes are included in the app's `Contents/Resources/Licenses` folder. Third-party source materials accompany the release separately. No sequencing data or previous analysis results are included in the download.
