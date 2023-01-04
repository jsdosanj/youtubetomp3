# youtubetomp3
Bash script to download videos from Youtube to mp3 format

#!/bin/bash

# Check if the YouTube-DL and FFmpeg packages are installed
if ! [ -x "$(command -v youtube-dl)" ] || ! [ -x "$(command -v ffmpeg)" ]; then
    echo "Error: YouTube-DL or FFmpeg is not installed."
    exit 1
fi

# Prompt for the YouTube URL
read -p "Enter the YouTube URL: " url

# Prompt for the output file name
read -p "Enter the output file name: " file_name

# Download the YouTube video using YouTube-DL
youtube-dl --extract-audio --audio-format mp3 $url

# Rename the downloaded file to the specified file name
mv *.mp3 $file_name.mp3

echo "Done."

To use this script, you will need to have the YouTube-DL and FFmpeg packages installed on your system. You can install these packages by running the following commands:
sudo apt-get update
sudo apt-get install youtube-dl
sudo apt-get install ffmpeg

To run the script, save it to a file and make it executable using the following command:
chmod +x download_youtube.sh

Then, you can run the script by typing "./download_youtube.sh" and following the prompts. The script will download the YouTube video and convert it to MP3 format, saving the file to the current directory.
