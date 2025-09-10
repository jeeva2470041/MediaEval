NewsImages 2025 – Image Retrieval (Team: ssn-coders)
Overview

This project is our submission to the MediaEval 2025 NewsImages Task.

Focused on the image retrieval subtasks (SMALL and LARGE).

Goal: Recommend the most relevant image for a given news article text.

Dataset

Used the official NewsImages 2025 dataset (~8,500 articles).

Each entry contains:

article_id,article_url, article_title, article_tags, image_id,  image_url and metadata.

Provided by the MediaEval organizers.

Method

CLIP (ViT-B/32): Extracted embeddings for both article text and images.

Feature fusion: Combined text and image features into joint embeddings.

Batch processing: Encoded features in chunks of 500 to manage GPU memory.

FAISS index: Built for efficient similarity search across 8,500 embeddings.

Retrieval: For each article title, retrieved the top-1 matching image.

Post-processing: Resized output images to 460×260 (PNG) as per task rules.

Usage

Install requirements:

pip install -r requirements.txt


Extract features (runs in batches, saves .npy + .csv):

python extract_features.py


Run retrieval (builds FAISS index and generates output images):

python retrieve.py

Results

Submission prepared in correct MediaEval format:

RET_CLIP_SMALL/ → subset task results.

RET_CLIP_LARGE/ → full task results.

Images named as:

[article_id]_ssn-coders_CLIP.png

Team

Team name: ssn-coders

Members:

G.Jeeva
E.Arivu Chezhiyan