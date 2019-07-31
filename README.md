This is a simple script to trascribe wav files using the Google machine learning engine

Please be aware the Google machine learning engine IS NOT FREE!!! Any charges you have
from using it are not my responsibility.

It uses the asterisk file nameing format: [timestamp].[calling].[receiving].wav

The output will be placed into directories by the receiving number.

The script creates a subshell for each call, you can set the block which will limit the number
of subshells it will create. You can run this number up until it freezes your machine. Keep an
eye on your load and don't allow it to go over the number of cores you have on your machine. It
runs much faster and cleaner if you keep your load health. The software was tested on a virtual
machine with 32 cores. (as well as one with 4 cores which didn't work well)

From my testing running 32 cores and a block of 240 call recordings at once yeilds results of just
under 20,000 transcriptions per hour for an average call length of 3 minutes.

Ths project was created for the need to transcribe half a million calls.

Future changes:
I would like to change the way the directory structure works so someone will be able to use
their own structure. However it's set up in the wav file directory will be how it shows up
in the log and trans directories.

Known bugs:
There is a Google limit which this software will hit. It's 300 transciptions pe 60 seconds and
no more than 480 hours of audio per hour. Google will get overrun with transcripts. You can go
to your Google metrics page and see the graphs of how many work and how many don't. You can 
tweek your block size to get it where you need. Once it's completed all the wav files just
run it again, the script will figure out where it didn't work and rerun it on those files until
my fix is in place.
	- I want to add a way to run this in parallel across multiple Google accounts. That is
	going to take some work and I don't know if I can use the gcloud software to do it.
	I may need to change things over and use curl statements. This will midigate the problem.
	- I could also add a retry feature, if one doesn't work it will retry it a number of
	times until it does.

