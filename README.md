# Youtube Transcript Summarizer
## Overview

This Python project uses Natural Language Processing (NLP) to generate concise summaries of YouTube video transcripts. By providing the URL of a YouTube video, users can retrieve the transcript, clean and preprocess the text, and generate summaries using two different approaches.

## Features
**Transcript Retrieval**: Fetches the transcript of a YouTube video using the YouTubeTranscriptApi library.

**Text Cleaning**: Removes unnecessary characters, punctuation, and stopwords to clean the transcript.

**Text Preprocessing**: Includes stemming, lemmatization, and removal of stopwords to prepare text for analysis.

**Summarization Options**:
  **Option 1**: Ranks sentences using word frequency and POS tagging (focuses on nouns and verbs).
  **Option 2**: Uses TF-IDF vectorization to select the most significant sentences.

**Customizable Output**: Users can specify the number of sentences in the summary.

## Getting Started
### Prerequisites
Python 3.8 or later
YouTube Data API Key (get it from the Google Cloud Console)
Required Python libraries:
  -youtube_transcript_api
  -nltk
  -spacy
  -numpy
  -re
  -sklearn
  -requests

## Installation
**Clone the repository or download the script.**

**Install the required Python libraries:**

pip install nltk spacy youtube-transcript-api numpy scikit-learn

**Download the SpaCy English model:**
python -m spacy download en_core_web_sm

**For NLTK, download the required data files:**
import nltk
nltk.download('stopwords')
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')

## Usage

1. Run the script.

2. Provide the YouTube video URL when prompted.

3. Specify the number of summary sentences required.

4. The script will output two summaries:

  Option 1: Word Frequency and POS Tagging-based summary.

  Option 2: TF-IDF-based summary.

**Example:**

Enter a YouTube video URL: https:https://www.youtube.com/watch?v=P6FORpg0KVo
Enter the number of lines of summary needed: 3

## Code Details

### Functions

**get_transcript(video_id):**

Fetches the transcript for a given video ID.

Combines all transcript entries into a single string.

**clean_text(text):**

Removes unwanted characters such as punctuation and extra spaces.

Strips leading/trailing whitespace.

**preprocess_text(text):**

Converts text to lowercase.

Applies stemming using PorterStemmer and lemmatization using SpaCy.

Removes stopwords using NLTK.

**summarizer1(text, n):**

Scores sentences based on word frequency of nouns and verbs.

Selects the top n sentences for the summary.

**summarizer2(text, n):**

Uses TF-IDF to calculate sentence significance.

Selects the top n sentences for the summary.

## Limitations

The quality of the summary depends on the clarity and structure of the video transcript.

The script may fail if the video transcript is unavailable or auto-generated with poor accuracy.

## Example Output
![Screenshot 2024-12-27 212032](https://github.com/user-attachments/assets/fda1c5d8-4d2c-4729-b707-9f030fd966c3)

