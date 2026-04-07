# BMET5995 Cochlear Sound Processing

This repository supports the BMET5995 assessment on cochlear implant sound processing. The work implements three strategies (F0F1F2, ACE, CIS) and produces electrodograms and frequency-time matrices from microphone input or .wav files.

## Assignment Overview
The assignment is in three parts:
- Part 1 (Week 10, individual, 10%): Python code, flowchart, one-page report.
- Part 2 (after Week 10, individual, 20%): oral quiz on the software’s technical operation.
- Part 3 (Week 12, group, 10%): research study and video presentation using a vocoder.

The goal is to implement and compare formant-based and spectral-peak (N-of-M) strategies, and to present results with appropriate documentation and citations.

## Sound Processing Strategies
- **F0F1F2** (formant-based): electrodes closest to formants 1 and 2 are stimulated according to formant amplitudes, with a fixed stimulation rate for this assignment.
- **ACE** (Advanced Combination Encoder): N-of-M spectral peak strategy, with an emphasis on stimulation presentation.
- **CIS** (Continuous Interleaved Sampling): N-of-M spectral peak strategy, differing from ACE primarily in presentation.

## Part 1 Deliverables (Week 10)
### 1) Python Code
**Allowed libraries only**
- soundfile
- numpy
- scipy
- matplotlib

**Functional requirements**
- Accepts input from microphone and from any standard `.wav` file up to 1 MB.
- Determines sampling frequency and resamples as required to a **standard internal rate of 16 kHz** (supports 4–64 kHz input).
- Processes audio into **2 ms epochs** with **6 ms Hann-window overlap** (3 ms before, 3 ms after).
- Processes each epoch using a user-selected strategy: **F0F1F2**, **ACE**, or **CIS**.
- Produces a **Frequency-Time Matrix (FTM)** stored as CSV:
  - 16 rows (electrodes 1–16; 1 is apical)
  - Columns represent 2 ms epochs
  - Stimulus amplitudes in **A = 0–1024**
  - Dynamic range limited to **10 dB**: AMAX/AMIN = 10^(10/20)
  - Fix C-level at **AMAX = 1024**
- Produces:
  - **Electrodogram** (heat-map, apical electrode at top)
  - **Time-domain plot** of the original audio
- All plots must include **titles, labeled axes, and legends where appropriate**.

**GUI requirements**
The program must run from an intuitive GUI containing:
- A file selector for `.wav` input
- Radio buttons to select **F0F1F2**, **ACE**, or **CIS**
- A time-domain plot window for the selected `.wav`
- An electrodogram plot window for the selected strategy
- Buttons labeled exactly:
  - `RUN`
  - `PLAY RESULT`
  - `PLAY WAV`

### 2) Flowchart
- One DIN A3 page (or equivalent PDF)
- Font size **≥ 8 pt** (Times New Roman or equivalent)
- Must match actual code logic and be understandable as a stand-alone document

### 3) One-Page Report (IEEE two-column format)
The report demonstrates code functionality using a provided sample sound.

**Required headings**
- Abstract
- Introduction
- Methods
- Results
- Discussion
- Conclusion

**Required content**
- Description of the origin, technical operation, and purpose of each strategy, based on **≥ 6 refereed journal/conference sources** (web-only sources are not acceptable).
- Electrodogram plot of the specified sound for **each** of the three strategies.
- Time-domain plot of the specified sound.
- Comprehensive reference list, including a statement acknowledging **all AI assistance** (what was used, and for what).

## Part 2 Deliverable (after Week 10)
### Oral Quiz (Individual, 20%)
An oral quiz will assess understanding of the software’s structure and operation, including:
- Strategy rationale and technical flow
- Electrodogram and FTM generation
- Sound processing steps and parameter choices
Python language-specific questions are not part of the quiz.

## Part 3 Deliverable (Week 12)
### Group Research Study (10%)
In groups of five or six, students will conduct a small study using a provided vocoder to compare strategy performance and present the results in a prepared video.

## Implementation Notes
- The stimulation rate is **fixed** for this assignment (formant strategies use a fixed rate rather than F0-based stimulation rate).
- The vocoder is provided in the assignment appendix; output should be compatible with the FTM format described above.

## Citation Requirement
All external sources must be cited, including:
- Publications describing the strategies
- Any AI assistance (tool, specific assistance provided)

## Suggested Repository Structure
This section is optional and can be updated to reflect your actual files.

```
BMET5995_Cochlear_Sound_Processing/
  README.md
  src/
    main.py
    gui.py
    processing/
      f0f1f2.py
      ace.py
      cis.py
    utils/
      audio_io.py
      plotting.py
  data/
    samples/
  outputs/
    ftm/
    plots/
```

## Quick Checklist (Week 10)
- GUI meets field/radio/button requirements
- WAV input + microphone input supported
- Resampling to 16 kHz handled (4–64 kHz inputs)
- 2 ms epochs, 6 ms overlap, Hann window
- F0F1F2, ACE, CIS strategies implemented
- FTM CSV output (16 rows, 2 ms columns)
- Electrodogram + time-domain plot labeled and titled
- Flowchart complete and matches code
- One-page report in IEEE format with required content

