# Pustaka Terbuka — UPNM (Universiti Pertahanan Nasional Malaysia)

> **Pustaka Terbuka: Katalog Induk Terbuka untuk Perpustakaan dan Sekolah Malaysia.**  
> *Official Perpustakaan Universiti Pertahanan Nasional Malaysia (UPNM) Bibliographic Dataset & Standalone Harvester.*

This repository contains the harvested open MARCXML collection and harvester pipeline for **Perpustakaan Universiti Pertahanan Nasional Malaysia** (`UPNM`), contributing to the national Malaysian union catalog at [pustaka-terbuka/opac](https://github.com/pustaka-terbuka/opac).

---

## Institutional Metadata

| Attribute | Value |
| :--- | :--- |
| **Institution Code** | `upnm` |
| **Agency Code** | `UPNM` |
| **Official Name** | Perpustakaan Universiti Pertahanan Nasional Malaysia |
| **Institution Type** | `university` |
| **State / Territory** | Kuala Lumpur |
| **Classification Scheme** | `LCC` |
| **OPAC Base URL** | [https://lib.upnm.edu.my/](https://lib.upnm.edu.my/) |
| **Platform / Engine** | `koha` |
| **Default Branch** | Perpustakaan Utama UPNM (Kem Sungai Besi) |

---

## Directory Structure

```text
upnm/
├── README.md                      # Institutional repository documentation
├── package.json                   # Node.js project specification & scripts
├── harvest/
│   └── inbox/upnm/             # Sealed MARCXML batch chunks and manifests
│       └── <run-id>-chunk-001/
│           ├── manifest.json      # Chunk SHA-256 manifest & metadata
│           ├── provenance.jsonl   # Record-level attribution and fetch logs
│           └── records/           # Batched MARC21 slim XML files
├── tools/
│   ├── harvesters/upnm/        # Automated OPAC crawler & MARC21 converter
│   ├── lib/                       # Supporting MARCXML, LCC, and validation utilities
│   ├── schemas/                   # JSON schemas for manifests and provenance
│   ├── validate-inbox.js          # Dataset integrity and schema validator
│   ├── merge.js                   # Local catalog merge engine
│   └── ingest-to-master.js        # Safe master ingestion bridge into pustaka-terbuka/opac
└── tests/
    └── harvester-upnm.test.js  # Autonomous test suite
```

---

## Usage

```bash
# Install dependencies
npm install

# Test run harvester (10 sample records)
npm run harvest:sample

# Run harvester with chunking
npm run harvest:chunked

# Validate dataset integrity
npm run validate-inbox harvest/inbox/upnm/<chunk-directory>

# Ingest new harvested batches into the central OPAC union catalog
npm run ingest:master
```

---

## Attribution & License

Dataset harvested and preserved under open library metadata standards for educational, civic, and cooperative indexing. Attribution: **Perpustakaan Universiti Pertahanan Nasional Malaysia (UPNM)** & **Pustaka Terbuka**.
