# Combined measurement of ECG, Breathing and Seismocardiograms (CEBSDB)

[![License: ODC-By 1.0](https://img.shields.io/badge/License-ODC--By%201.0-green)](https://opendatacommons.org/licenses/by/1-0/)
[![Access: public](https://img.shields.io/badge/access-public-0e8a16.svg)](https://physionet.org/content/cebsdb/1.0.0/)

**Combined measurement of ECG, Breathing and Seismocardiograms (CEBSDB)** — simultaneous ECG, respiration, and seismocardiogram recordings; PhysioNet open access.

- **Dataset repository**: https://github.com/biometric-community/MIT-BIH-Combined-measurement-of-ECG-Breathing-and-Seismocardiograms
- **Upstream source**: https://physionet.org/content/cebsdb/1.0.0/
- **DOI**: https://doi.org/10.13026/C27G6P
- **Original format**: PhysioNet WFDB (`.dat` / `.hea`) under `data/`
- **License (data)**: [Open Data Commons Attribution License v1.0](https://opendatacommons.org/licenses/by/1-0/) (PhysioNet)
- **License (helpers / docs)**: CC BY 4.0 (see [`LICENSE`](LICENSE))

| Field | Value |
|-------|-------|
| Catalog id (tbiom) | `cebsdb` |
| Category | `physio` |
| Access | `public` |
| PhysioNet / WFDB slug | `cebsdb` |
| Upstream homepage | https://physionet.org/content/cebsdb/1.0.0/ |
| Paper alias | CEBSDB (e.g. Abdeldayem & Bourlai, TBIOM 2019 spectral-correlation ECG ID) |

## TL;DR

- **Task**: multi-modal cardiorespiratory analysis / ECG identity benchmarking
- **Modality**: ECG + respiration + seismocardiogram (WFDB `.dat` / `.hea`)
- **Platform**: CEBSDB PhysioNet recordings (basal / music / post conditions)
- **Real/Synthetic**: real
- **Subjects / records**: **20** subjects; **60** records (`b*` / `m*` / `p*`)
- **Sampling**: **5 kHz**
- **Citation**: see PhysioNet CEBSDB page

## Download

- **This repository**: WFDB records under [`data/`](data/) (when populated). Large `.dat` files use Git LFS.
- **Upstream**: https://physionet.org/content/cebsdb/1.0.0/
- **Helper script** (from tbiom monorepo root):

```bash
bash projects/datasets/scripts/download_cebsdb.sh
```

Preferred (after `pip install wfdb`):

```bash
python -c "import wfdb; wfdb.dl_database('cebsdb', r'projects/datasets/cebsdb/data')"
```

## Dataset structure

```text
cebsdb/
├── README.md
├── LICENSE
└── data/
    ├── RECORDS
    ├── b001.dat / .hea
    ├── m001.dat / .hea
    └── …
```

## Quick start

```python
import wfdb

rec = wfdb.rdrecord("data/b001")
print(rec.sig_name, rec.fs, rec.p_signal.shape)
```

## License

- **Data** (PhysioNet CEBSDB): [ODC-By 1.0](https://opendatacommons.org/licenses/by/1-0/)
- **Helpers / docs** in this repository: [CC BY 4.0](LICENSE)

## Citation

Please cite the PhysioNet CEBSDB publication and the PhysioNet resource itself when using these data. See https://physionet.org/content/cebsdb/1.0.0/ for the recommended citations.

## Contact

- Upstream / PhysioNet: https://physionet.org/content/cebsdb/1.0.0/
- This mirror: https://github.com/biometric-community/MIT-BIH-Combined-measurement-of-ECG-Breathing-and-Seismocardiograms
