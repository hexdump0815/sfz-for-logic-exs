# sfz mappings for some of the logic exs samples

this is the result of investing quite a bit of time to convert a bunch (mostly the important, orchestral, piano and guitar packages) of the default logic exs files to sfz using the exs2sfz tool from https://www.bjoernbojahr.de/exs2sfz.html ... not all of them are working well, but most of them do. you can use them for instance with the open source sfizz sampler from https://sfz.tools/sfizz/ ...

to use them just clone this repo (or get the zip from github) somewhere and create the following symbolic links inside of the logic-9 and logic-x directories (depending of which one you have installed):

```
cd logic-9
ln -s '/Library/Application Support/Logic/EXS Factory Samples' 'EXS Factory Samples'
ln -s '/Library/Application Support/GarageBand/Instrument Library/Sampler/Sampler Files' 'Sampler Files'
cd ..
cd logic-x
ln -s '/Library/Application Support/Logic/EXS Factory Samples' 'EXS Factory Samples'
ln -s '/Library/Application Support/GarageBand/Instrument Library/Sampler/Sampler Files' 'Sampler Files'
```

the procedure to create them was the following:
* convert the exs file using exs2sfz (see above - it even works on linux with wine if you do not have windows around)
* adjust the default_path entry in the resulting sfz file to point to the symbolic links from above (relative to the position of the sfz file)
* some exs files cannot be converted using the exs2sfz tool

while we are at it: there is also some workflow to convert kontakt libraries with certain settings to sfz - you need a mac with eiher mainstage 3.2+ or logic pro x 10.5+ (both incluse the autosampler) and the free kontakt player. just load the kontakt player into the autosampler and the kontakt library you want to sample into it, do the settings as you like and autosample it (there are a lot of tutorials around on the net). this will result in an exs sample, which sadly cannot be converted with exs2sfz, but there is another tool: https://github.com/shinybit/autosampler2sfz.py.git which can build a sfz file from the samples in it. please respect the copyright of the instruments you are sampling and make sure they are either public or you own them. a good source for interesting and freely available sample libraries is the pianobook project: https://www.pianobook.co.uk/ ...
