# voiceCloneTts

## original source information 
- https://rioharper.medium.com/cloning-your-voice-cb321908b060#22d2
- good instructions for dealing with errors that might occur: `https://github.com/coqui-ai/TTS/discussions/1074` 

## some of my notes:

- local testing of step1: 
    - install pyaudio on mac osx within pyenv: https://gist.github.com/jiaaro/9767512210a1d80a8a0d
        - `brew install portaudio` 
        - then install the libraries locally, avoid doing a virtualenv because of the audio issues 
        - for requirement ffmpeg, make sure ffmpeg-python is installed in pip just in case
    - then run `python Part1_speech_dataset_wizard.py` to help create the audio files for test 
    - when running, no need to install the touch github directly, just use pip install 
    - when looking at the config file, change name=`LJSpeech` - this is the base name for the model 
    - for dealing with small sample size, change these configs in the config = part of `train_vits.py`: 

 ```
 config = VitsConfig(
                audio=audio_config,
                run_name="vits_ljspeech",
                batch_size=2, #original here was 32 
                eval_batch_size=2, #original here was 16
                eval_split_size=2, #this was not in here originally
                batch_group_size=2, #original here was 5 
                num_loader_workers=0,
                num_eval_loader_workers=4,
                run_eval=True,
                test_delay_epochs=-1,
                epochs=1000,
                text_cleaner="english_cleaners",
                use_phonemes=True,
                phoneme_language="en-us",
                phoneme_cache_path=os.path.join(output_path, "phoneme_cache"),
                compute_input_seq_cache=True,
                print_step=25,
                print_eval=True,
                mixed_precision=True,
                output_path="/content/drive/MyDrive/VoiceCloning/output",
                datasets=[dataset_config],
            )
```
- when running part 3, model - needed to create nested .wav folders; and double add .wav - need to figure this out 




### original source information 
- https://rioharper.medium.com/cloning-your-voice-cb321908b060#22d2
- good instructions for dealing with errors that might occur: `https://github.com/coqui-ai/TTS/discussions/1074` 
- `conda create -n dataset pyaudio ffmpeg`
- `pip install -r requirements.txt`
- run this if you are on linux as well: 
`sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev libxi-dev libxkbcommon-dev libxkbcommon-x11-dev`
- 
