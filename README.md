This repository provides the data and analysis materials used in our study on ankle joint stiffness, dynamic stability, and EMG outcomes during obstacle crossing, comparing dominant and non-dominant limbs.

The repository includes:
- Raw **C3D** files for a de-identified subset of participants (**n = 8**).
- **Visual3D** processing materials (model template + pipeline command scripts) to reproduce biomechanical/EMG outcome computations.
- **SPSS** output files containing the primary statistical results reported in the manuscript.

---

## Repository Structure

## Repository Structure

├─ c3d files/
│  ├─ SUBJ_01/   (21 C3D files: 20 dynamic trials + 1 static calibration)
│  ├─ SUBJ_02/
│  ├─ ...
│  └─ SUBJ_08/
│
├─ spss results/
│  ├─ *.spv      (2 files: SPSS Viewer outputs)
│
└─ v3d files/
   ├─ template/  (Visual3D model template)
   └─ *.v3s      (2 files: Visual3D pipeline command scripts)

---

## Data Description

### 1) C3D files (`c3d files/`)
- The folder contains 8 participant subfolders: `SUBJ_01` to `SUBJ_08`.
- Each participant folder contains **21 C3D files**:
  - **20** dynamic trials (formal test trials)
  - **1** static calibration trial (static standing calibration)

#### EMG signals within C3D
EMG data are embedded in the C3D files as analog channels. The channel order is:

| C3D Analog Channel | Muscle (CN) | Muscle (EN) |
|---|---|---|
| EMG.v1  | 左股二头肌 | Left Biceps Femoris (BF) |
| EMG.v2  | 左股外侧肌 | Left Vastus Lateralis (VL) |
| EMG.v3  | 左股内侧肌 | Left Vastus Medialis (VM) |
| EMG.v4  | 左股直肌   | Left Rectus Femoris (RF) |
| EMG.v5  | 左腓骨长肌 | Left Peroneus Longus (PL) |
| EMG.v6  | 左腓肠肌   | Left Gastrocnemius (GAS) |
| EMG.v7  | 左胫骨前肌 | Left Tibialis Anterior (TA) |
| EMG.v8  | 左比目鱼肌 | Left Soleus (SOL) |
| EMG.v9  | 右股二头肌 | Right Biceps Femoris (BF) |
| EMG.v10 | 右股外侧肌 | Right Vastus Lateralis (VL) |
| EMG.v11 | 右股内侧肌 | Right Vastus Medialis (VM) |
| EMG.v12 | 右股直肌   | Right Rectus Femoris (RF) |
| EMG.v13 | 右腓骨长肌 | Right Peroneus Longus (PL) |
| EMG.v14 | 右腓肠肌   | Right Gastrocnemius (GAS) |
| EMG.v15 | 右胫骨前肌 | Right Tibialis Anterior (TA) |
| EMG.v16 | 右比目鱼肌 | Right Soleus (SOL) |

> Note: Participant identifiers are de-identified codes (SUBJ_01–SUBJ_08). No personally identifying information is included.

---

### 2) SPSS results (`spss results/`)
This folder contains **two `.spv` files**, which can be opened with **IBM SPSS Statistics** (SPSS Viewer).  
They include the statistical outputs for the primary outcomes reported in the manuscript, including:
- **Ankle joint stiffness**
- **Dynamic stability**
- **EMG-related outcomes** (derived from the embedded EMG channels listed above)

---

### 3) Visual3D files (`v3d files/`)
This folder contains materials required to reproduce the outcome computations in **Visual3D**:
- `template/`: Visual3D **model template** used in the study
- `*.v3s` (2 files): Visual3D **pipeline command scripts** used to compute ankle stiffness, dynamic stability, and EMG outcomes

---

## How to Reproduce the Analysis (Visual3D)

### Prerequisites
- **Visual3D** (version compatible with `.v3s` scripts and the provided template)
- Ability to import **C3D** files (including analog EMG channels) in Visual3D

### Suggested workflow
1. Open Visual3D and create a new workspace/project.
2. Import the C3D files for one participant (e.g., `c3d files/SUBJ_01/`):
   - Import the static calibration trial first (recommended).
   - Import the 20 dynamic trials.
3. Load/apply the provided **template model** from `v3d files/template/`.
4. Run the provided **pipeline command scripts** (`.v3s`) in `v3d files/` to compute:
   - ankle joint stiffness
   - dynamic stability metrics
   - EMG-derived outcomes (from EMG.v1–EMG.v16 in the C3D analog channels)
5. Export computed outcomes as needed for downstream statistics.

> Tip: If your Visual3D workflow requires path remapping, update file paths after importing the data, then re-run the `.v3s` scripts.

---
