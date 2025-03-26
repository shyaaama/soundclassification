
Sound Classification and Recommendation System

📌 Project Overview

This project focuses on sound classification and music recommendation using cosine similarity. The dataset consists of various audio files belonging to different genres. We extract features, analyze similarities, and recommend songs based on user input.

🔧 Technologies Used

Python

NumPy, Pandas

Librosa

Scikit-learn

Matplotlib & Seaborn

IPython.display (for audio playback)

📂 Dataset

The dataset contains 30-second audio clips categorized into different genres. Each file follows the naming convention:

genres_original/<genre>/<genre>.<file_id>.wav





🎼 Feature Extraction

We extract features from audio files using Librosa:

import librosa
import librosa.display
import numpy as np

audio, sr = librosa.load("path/to/audio.wav")
features = librosa.feature.mfcc(y=audio, sr=sr, n_mfcc=13)

🎵 Music Recommendation System

1️⃣ Standardizing Data

from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
data_scaled = scaler.fit_transform(data)

2️⃣ Computing Similarity

from sklearn.metrics.pairwise import cosine_similarity
similarity = cosine_similarity(data_scaled)

3️⃣ Generating Recommendations

def find_similar_songs(song_name):
    series = sim_df_names[song_name].sort_values(ascending=False)
    series = series[1:6]  # Remove self-match
    print("Recommended songs for:", song_name)
    print(series)

