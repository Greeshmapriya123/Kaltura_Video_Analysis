# Kaltura Engagement Analysis Report

A short, human-friendly wrap of the Kaltura student video engagement study. The notebooks here explore how video length impacts completion and drop-off, and package the analysis into a shareable HTML report.

## What’s here
- `kaltura_engagement_pipeline.ipynb`: data cleaning and feature prep (timestamps, unit normalization, drop-off guards).
- `video_length_vs_dropoff_analysis.ipynb`: analysis and visuals (completion vs. length, drop-off trends, density maps).
- `kaltura_engagement_analysis_report.html`: exported narrative report for quick GitHub viewing.
- `requirements.txt`: minimal Python stack to rerun the notebooks.
- `LICENSE`: MIT license.

## Quick start
1) Install deps: `python -m venv .venv && .venv\\Scripts\\activate && pip install -r requirements.txt`
2) Launch notebooks: `jupyter notebook` and open the two `.ipynb` files in order (pipeline, then analysis).
3) To regenerate the HTML report: from Jupyter, `File → Download as → HTML` on `video_length_vs_dropoff_analysis.ipynb` (or use `nbconvert --to html video_length_vs_dropoff_analysis.ipynb`).

## Data notes
- Source data is not included; keep raw student records private. Point the pipeline to your local CSVs and ensure identifiers are removed or anonymized.
- The analysis expects cleaned session-level data with length, completion, and drop-off fields; adjust column names in the pipeline if yours differ.

## Key findings (humanized)
- Shorter videos win: completion drops sharply after ~15 minutes; 5–15 minutes is the sweet spot.
- Longer lectures suffer early exits: drop-off accelerates with runtime; hour-long sessions lose most viewers.
- Design implication: break long lectures into concise segments and open strong to capture the critical first minutes.

## Repo hygiene
- `.gitignore` keeps checkpoints, virtualenvs, and local data out of version control.
- Prefer committing lightweight, de-identified samples or schemas instead of full raw datasets.

## How to adapt
- Swap in your own datasets by updating the input paths in `kaltura_engagement_pipeline.ipynb`.
- Tweak bucketing or visual styles in `video_length_vs_dropoff_analysis.ipynb` to match your audience.
