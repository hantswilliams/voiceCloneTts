# voiceCloneTts

- local testing of step1: 
    - install pyaudio on mac osx within pyenv: https://gist.github.com/jiaaro/9767512210a1d80a8a0d
        - `brew install portaudio` 
        - then install the libraries locally, avoid doing a virtualenv because of the audio issues 
        - for requirement ffmpeg, make sure ffmpeg-python is installed in pip just in case
    - then run `python Part1_speech_dataset_wizard.py` to help create the audio files for test 
    



### original source information 
- https://rioharper.medium.com/cloning-your-voice-cb321908b060#22d2
- `conda create -n dataset pyaudio ffmpeg`
- `pip install -r requirements.txt`
- run this if you are on linux as well: 
`sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev libxi-dev libxkbcommon-dev libxkbcommon-x11-dev`
- 
