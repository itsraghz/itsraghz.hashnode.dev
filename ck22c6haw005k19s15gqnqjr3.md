## TIL - Asciinema - awesome terminal recording utility

Hey @[Hashnode Developer](@HashnodeDev) folks, 

This is my post to the #TIL (Today I Learnt) Series.

 I have learnt about an interesting tool called [**Asciinema**](https://asciinema.org/) - if you want to split and read, it is ASCII Cinema. It is a simple, lightweight and awesome utility that records the activities on your terminal and saves it as a less sized text file with a ```.cast``` extension.

### To Install 
You can install this via 
```
apt-get install asciinema
```
A quick start on this tool.

### To Start recording - with the default file name

```
asciinema rec 
```
Press Enter. The utility will start recording all the activities, - from the commands you enter (every key press - including backspace, delete etc.,  :)) and the intermediate changes/text if any happening on the screen (in case of installation of tools like ```@angular/cli```) and the final output displayed on the terminal (for the typical unix commands like ```ls```, ```cat``` etc., )

Press ```ctrl+d``` to stop the recording. The tool tells you the file name and its location. By default it gets saved into **/tmp** and with a cryptic name with a ```.cast``` extension.

### To start recording - with your own file name

```
asciinema rec <yourFileNameWithLocation>
```
You can give a file name of your choice with the location of course. 

> The file extension should be .cast as that is a mandatory for the tool to play it further.

### To Play the recorded file 

```
asciinema play <fileName>.cast
```
This command will literally play the commands and the outputs what you have entered. This is a good refresher to you to look at what was happening to the System and the step by step you had been progressing. 

### Upload to the Server

If you want, you can upload the recording to the Server by using the ```upload``` argument.* I have not tried this yet. *

### Benefits 

It would be really useful if you want to do a screen capture for the learning, tutorial series etc., 

I am sure every command line / terminal fanatic, would love this tool for sure, like me :) #HappyLearning...