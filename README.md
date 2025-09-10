# MediaEval
We implemented an image retrieval system for MediaEval 2025 NewsImages using CLIP and FAISS. News article titles and tags are encoded with CLIP, combined with image features, and indexed in FAISS. For each query, the system retrieves the most relevant image, resized to 460×260, and saved in the required format.
