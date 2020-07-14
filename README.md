# Audio telegram bot

## Content
* [Definition of crawler](#def)
* [Dependencies](#dependencies)
* [How to run programs](#run)
  * [Dataset assembling](#asm)
  * [learn the model and execute bot](#bot)
# <a name="def"></a> Definition of telegram bot

Bots are simply Telegram accounts operated by software – not people – and they'll often have AI features. They can do anything – teach, play, search, broadcast, remind, connect, integrate with other services, or even pass commands to the Internet of Things.

# <a name="dependencies"></a> Dependencies

**Debian/Ubuntu/Mint**

``` sudo apt-get install python3```

**Fedora/CentOS**

```sudo dnf install python3```

#### librosa
```
pip3 install librosa
```

#### numba 0.48.0
```
 pip3 install numba==0.48.0
```

#### sklearn
```
pip3 install sklearn
```

#### pytelegrambotapi
```
pip3 install pytelegrambotapi
```

# <a name="run"></a> How to run program

## <a name="asm"></a> Dataset assembling
Dataset assemles from audio records with 5 digits in it. We need to despite this audio to 5 audios with digits and put this wav's to current directories.
To assemble the dataset we used to special programs for it:

* adio_digits_dataset_bot.py
* split_by_vad.py
    
Execute the audio dataset.
This program executes bot that listens 5 digits that you say and put them down to the folder.
So, execute the your bot with telegram write text request(you receive message with digits) and dictate this digits to bot.
```
audio_digits_dataset_bot.py
```
Then you need to split this audio. For this program exists program.
This program splits one audio with 5 digits to 5 with 1 digit. And pulling them to the current each other folder.
```
    python3 split_by_vad.py dataset/wav/1_2_3_4_5.wav 0.1 0.01 dataset/splitted/
```
First argument is depth of the human voice. Second argumaent is the step that we walk on the audio.


## <a name="bot"></a> learn the model and execute bot

a)All code to execute model learning contains in ml.ipynb:
```
    jupyter notebook ml.ipynb
```
You can just execute this code to down cell. 

b) Now you can execute your bot:
```
    python3 audio_digits_recognition_bot.py
```
