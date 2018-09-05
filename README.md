# Intro

This repository contains a tool to provide automatic punctuation of lecture transcripts obtained from YouTube. YouTube's transcripts are automatically generated by Google's automatic speech recognition (ASR) functionality, but are not punctuated. My tool is specially configured to punctuate lecture transcripts, since transcripts can be helpful to learners for a variety of reasons. The tool's current average F-score for correctly punctuating transcripts of lecture videos using commas, periods, question marks and semicolons is 67.3. Note that this F-score will probably be much lower if you try my tool on non-lecture or non-educational videos as the context will be different.

My work on this tool slightly builds upon that of https://github.com/ottokart/punctuator2, from which my repository is forked. I used the training structure in that repository to train a customized bidirectional recurrent neural network on manually punctuated transcripts scraped from Udacity's YouTube channel (https://www.youtube.com/user/Udacity) and from Princeton's COS226 class on Coursera (https://www.coursera.org/learn/algorithms-part1/ and https://www.coursera.org/learn/algorithms-part2). The training data that was used can be found in the "training_data" subdirectory inside the root of this repository. For more information and details regarding the background and methodology for training the neural network and regarding the project in general, including possible ways to improve the F-score, please refer to the "final_report.pdf" file in the root of the repository. Please note that some of the things in the report might be outdated or irrelevant to this repository's functionality.

# Requirements

* Python 2.7+
* pip (if it is not installed on your system, install with `sudo apt-get install python-pip`)
* Theano (if it is not installed on your system, install with `sudo pip install Theano`)
* youtube-dl (if it is not installed on your system, install with `sudo apt-get install youtube-dl`)
* ffmpeg (if it is not installed on your system, install with `sudo apt-get install ffmpeg`)
* The neural network file: download the file then place it in the root directory of the repository: https://drive.google.com/file/d/1AyBk8NHyOuf_JgKo0AUeZr_O0w9PJD2a

# Usage

If you have a link to a YouTube lecture video or playlist, simply execute `python lecture_punctuator.py <YouTube_link>`, where `<YouTube_link>` could be the link of a YouTube video, playlist, or channel. The program will output the transcript(s) in the current working directory to a subdirectory called "transcripts". Please make sure that the path to `lecture_punctuator.py` is configured correctly. The output format for a transcript is `<Video Title>_<YouTube ID>`.
