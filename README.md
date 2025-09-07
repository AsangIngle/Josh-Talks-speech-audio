1. Project Overview

Hindi ASR & Disfluency Detection

This project involves building a Hindi ASR pipeline using Whisper, and detecting various speech disfluencies (fillers, repetitions, false starts, prolongations, hesitations) from ~10 hours of conversational audio.

1.Key components include:
2.Dataset creation and processing
3.ASR model preparation and fine-tuning
4.Disfluency detection and segmentation
5.Output metadata and segmented audio clips for each disfluency occurrence

2. Repository Structure
   Josh-Talks-speech-audio/
├── dataset_preparation/         # Code & scripts for dataset setup
├── fine_tuning/                 # Whisper model fine-tuning notebook(s)
├── disfluency_detection/        # Detection & segmentation notebook(s)
├── output/                      # Generated CSVs, audio segments
├── resources/                   # Disfluency lexicons, metadata
├── LICENSE                      # (If applicable)
└── README.md                    # This file
3. Components Overview
Dataset Preparation

Notebooks and scripts that:

Download and extract the dataset

Clean and standardize audio (16 kHz, mono)

Prepare train, validation, test splits
Link: Shared Google Drive dataset link

Model Fine-Tuning

Includes a Jupyter notebook (e.g., JoshTalk_final_code_2.ipynb) that:

Loads Whisper (small model)

Trains/fine-tunes on the prepared dataset

Reports initial accuracy / WER metrics
Due to hardware constraints, training couldn’t be completed fully. The accuracy reported corresponds to earlier runs.

Disfluency Detection & Segmentation

Notebook (e.g., task_3_joshtalk.ipynb) that:

Uses Whisper to transcribe segments with timestamps

Detects disfluency types via lexicon and regex

Clips and exports audio for each detected disfluency segment

Generates a structured CSV sheet – one row per disfluency occurrence

4. Usage Instructions

Prerequisites:

Python 3.x environment

Libraries: whisper, librosa, pydub, pandas, regex, etc.

Adequate storage to handle audio data

Steps:

Setup Dataset:

Download audio + transcriptions from the provided link.

Run the dataset preparation notebook to clean and split.

(Optional) Fine-Tune ASR Model:

Execute the fine-tuning notebook.

Note: GPU constraints limited full training — accuracy reported is from partial runs.

Run Disfluency Detection:

Use the disfluency notebook to process segments, detect disfluencies, clip audio, and output results.

View Results:
disfluency_id, recording_id, start_time, end_time, type, transcript, clip_path
5. Limitations & Work-in-Progress

Hardware Constraints: Limited GPU resources prevented thorough execution of the full pipeline across the 10-hour dataset.

Examination Commitments: Academic exams affected available time for full experimentation.

As a result, the current version contains working prototypes and partial outputs. However, the pipeline logic and code structure are fully implemented and ready to scale.

6. Acknowledgements & References

Dataset Source: Provided via Google Drive (link)

Model Framework: Whisper (OpenAI)

Audio Processing: Librosa, Pydub

Disfluency Patterns: Custom lexicon + regex rules (fillers, repetitions, etc.)
