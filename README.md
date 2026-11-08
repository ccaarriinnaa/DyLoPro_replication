# __DyLoPro: Profiling the Dynamics of Event Logs - *Replication*__

This repository contains our replication of the DyLoPro paper, made for the Process Analytics Seminar (2IMI00) at TU/e by Carina Ungureanu and Sujitha Navaneetha Krishnan. It is based on the authors' [case studies repository](https://github.com/BrechtWts/DyLoPro_CaseStudies). We reran their BPIC17 and BPIC19 notebooks and applied the same analysis to two new public event logs, **Sepsis Cases** and **Road Traffic Fines Management**.

**Original paper:** Wuyts, B., Weytjens, H., vanden Broucke, S., De Weerdt, J.: DyLoPro: Profiling the dynamics of event logs. BPM 2023, LNCS vol. 14159, pp. 146–162. Springer (2023). https://doi.org/10.1007/978-3-031-41620-0_9

## __1. DyLoPro Python Library__
The __DyLoPro Python library__ lets you explore how an event log changes over time, from the control-flow, data and performance perspectives.
We used __DyLoPro 0.1.1__. This version does not work with pandas 3, so pandas has to stay below 3:

```bash
pip install DyLoPro pm4py "pandas>=2.0,<3.0" notebook
```

Our environment:

| Item | Version (RFTM) | Version (Sepsis) | 
|---|---|---|
| Python | 3.11.14 | 3.14.7 | 
| DyLoPro | 0.1.1 | 0.1.1 | 
| pandas | 2.2.2 | 2.3.3 |
| numpy | 1.26.4 | 2.5.3 |
| matplotlib | 3.10.8 | 3.11.2 |
| pm4py | 2.7.23.10 | 2.7.23.10 |
| Hardware | Windows 11 laptop, AMD processor (AMD64 Family 25 Model 116) | Windows 11 laptop, AMD processor (AMD64 Family 25 Model 116) |

## __2. Case studies__

The notebooks in this repository are:

1. __BPIC_19.ipynb__: the authors' case study on the BPIC19 event log, rerun by us. The data can be found [here](https://doi.org/10.4121/uuid:d06aff4b-79f0-45e6-8ec8-e19730c248f1).
1. __BPIC_17.ipynb__: the authors' case study on the BPIC17 event log, rerun by us. The data can be found [here](https://doi.org/10.4121/uuid:5f3067df-f10b-45da-b98b-86ae4c7a310b).
1. __Sepsis.ipynb__: *new.* Our case study on the __Sepsis Cases__ event log. The data can be found [here](https://doi.org/10.4121/uuid:915d2bfb-7e84-49ad-a286-dc35f063a460) (downloaded 2026-10-14). Plots are saved in `figures_sepsis/`, tables and `run_manifest.json` in `results_sepsis/`.
1. __RTFM_DyLoPro_replication.ipynb__: *new.* Our case study on the __Road Traffic Fines Management__ event log, which the authors list as "coming soon". The data can be found [here](https://doi.org/10.4121/uuid:270fd440-1057-4fb9-89a9-b699b47990f5) (downloaded 2026-10-26). Plots are saved in `figures_rtfm/`, tables and `run_manifest.json` in `results_rtfm/`.

`preprocess_case_studies.py` is the authors' script that turns the BPIC17 and BPIC19 logs into `BPIC17.csv` and `BPIC19.csv`.

## __3. How to run__

1. Download the event logs from the links above and put them in this folder. They are not included here because they are too large.
1. For BPIC17 and BPIC19, first run `python preprocess_case_studies.py`.
1. Open a notebook and run all cells.

The notebook outputs are cleared to keep the files small, so the plots only show up after running. Our own results for Sepsis and RTFM are already saved in the `figures_*` and `results_*` folders. DyLoPro has no random elements, so rerunning gives the same results.
