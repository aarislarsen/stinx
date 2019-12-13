# Stinx
Stinx - Stuff Indexer - is a lightweight tool to make tools, files, notes etc. tag'able and searchable on your local PC.

## Background
I hoard data, scripts, installers, notes, guides, payloads etc. My thinking is "I'll have use of that later" or after I've used something "I might need this again some day". But when that day comes, I can't seem to remember where I put it.
So of course, I devised an intricate folder structure, split into disciplines, tool categories, payloads, samples, directory listings etc. And all was good, for a time.
But soon I found there to be too much crossover. Samples began also including payloads, articles and notes melted together, and tools no longer fit neatly into single categories, but had dual purposes.
So I made this to make it easier for me to find my stuff.

## Instalation
1. Download the files and stuck them in a folder somewhere
2. Edit the StinxCmd.dll.config and change the current "watchpaths" (being the root of your C-drive) to the location you want to be searchable. You can specify multiple paths by separating them with a comma
3. Run the StinxCmd.exe

## How it works
When started, Stinx runs through your watchpaths looking for Stinx-files. This only takes a second. A Stinx-file is basically just a .txt file but with the .stinx suffix, and must contain the following fields at the top:
```
[stinx][title]Some descriptive title
[stinx][abstract]A brief description of the content
[stinx][tags]a,number,of,separated,tags,that,you,can,search,for
```
An example would be my notes on persistence mechanisms:
```
[stinx][title]Windows Persistence mechanisms
[stinx][abstract]All the different ways attackers and malware can persist on a Windows system
[stinx][tags]windows,persistence,persist,wmi-parser
```
After this "header" the actual notes and details follow.

Stinx lets you search these files either as plain-text search, or search by tags and sorts the results in order of hits.
Each result comes with a "selection number", and when entered it will open up Explorer to that file, for you to open and start using.

So lets say you had a tool, an executable or an installer that you've stuck in a folder somewhere. For that file, you'd make an accompanying .stinx file with the same name as the actual file, include an abstract and some relevant tags in the Stinx header. Now you can search for it, and it will put you in the right folder to run the installer or deal with any other files that are associated with that tool.
