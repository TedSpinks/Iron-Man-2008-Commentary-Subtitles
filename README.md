# Iron Man (2008) Commentary Subtitles

There is an amazing live audio commentary track with Jon Favreau and Robert Downey, Jr. floating around the Internet. I found that their commentary totally enhanced my enjoyment of the movie. BUT it was recorded with a live crowd in a very noisy theater so at times it was ***very hard to hear*** what they were saying.

This project is my attempt to rectify that: a subtitle (SRT) file to play along with the audio.

Additional details about this audio commentary:

- It was recorded from a live showing of the movie with Jon Favreau and Robert Downey, Jr. at the Santa Monica Aero Theater on September 6th, 2008.
- Original recording source: https://www.reddit.com/r/movies/comments/4lwrt4/there_was_no_official_directors_commentary_for/

## Project Goals

This project is an attempt to make Jon and Robert's great commentary easier to enjoy:

- Find a solution for the hard-to-hear audio.
- Produce a final track that can be remuxed into an MKV rip of the Blu-Ray for seamless listening and viewing.

## Improve Audio Quality?

Since there is a LOT of background noise from the crowd in the theater, it would be ideal to filter some of that out, so it's easier to hear Jon and Robert.

- TLDR: I tried and failed to improve the quality of the audio.
- In the Reddit thread, **Idlepenguin** posted [this attempt](https://soundcloud.com/user-409086453/iron-man-live-commentary-quick-fix) to do just that. I thought that while it made some parts of the dialog easier to hear, it also made other parts harder to hear. While Idlepenguin's edit wasn't for me, I can certainly see why others found it to be an improvement. And after attempting to do something similar, I do think Idlepenguin probably got the best result possible given the state of the source material - it's much better than my attempts!
- My attempts:
	- I tried iZotope RX 11 (free version), both its voice isolate and repair features, but they couldn't seem to tell Jon and Robert from the crowd.
	- I tried Adobe Podcast Enhance. It is apparently limited to 2 hrs, so if the result had been good, I suppose I'd have had to find a good cut point to split the audio file. Again, I thought the result was really choppy, like it couldn't tell Jon and Robert from the crowd.

## Improve via Subtitles!

Plan B: Add a subtitle track so we can fully enjoy Jon + Robert's conversation, despite the less-than-ideal audio situation.

- First, I synced the audio track to the video as best I could - see [Syncing Up the Audio](#syncing-up-the-audio) below.
- I tried [Krisp.ai](https://krisp.ai)'s transcription feature since I already had an account, but it had a really hard time hearing Jon + Robert above the noise of the crowd. It did a poor job. 
- I payed for a $20/month subscription to [TurboScribe.ai](https://turboscribe.ai). It did a really good job transcribing - easily as good as a human listener would do in 1 or 2 passes! And it had native SRT exporting for the win!!
- The resulting SRT file still needed a LOT of work:
	- There were many, many sentences that took up 3 or 4 lines of the screen, and many more that weren't on the screen for long enough to read. I used [claude.ai](https://claude.ai) to split these up, combine lines where a sentence ended on a single word or two, and finally add buffer time to each line (but without overlapping with the next line) so that us humans have enough time to read them.
	- I used [Aegisub](https://www.audacityteam.org/) to make lots of little edits and dialog fixes while I watched the film (it shows Characters Per Second for each line, has find/replace, etc.). There were so many things TurboScribe misheard! These were often moments of audio that were very, very hard to hear! Playing them back over and over again wasn't enough - I had to figure them out from context and by googling surrounding aspects of Jon and Robert's conversation. This part of the process took many hours!

## Syncing Up the Audio

I used [Audacity](https://www.audacityteam.org/) to sync up the original MP3 audio with my Blu-Ray video:

- Removed the first ~7 minutes which take place before the theater started playing the movie.
- Synced the audio to the conversation in the Humvee at ~2 min.
- Despite syncing to the beginning, I found that by the end of the movie the audio was out of sync (too short) by a full minute!
- Fixed this by stretching the track to sync up with Stark's "I *am* Iron Man" line at the end of the movie.
	- While the sync wasn't quite perfect, I got it to where it was < 1 sec off throughout the movie, which is close enough for a commentary track (it's not uncommon for them to be slightly out of sync).
	- Interestingly, there are a couple moments during the movie where the stretched track does sync up perfectly, so I wonder if the theater's projection wasn't quite as consistent as a 100% digital Blu-Ray?
- Trimmed ~30 min of post-movie Q&A from the end so that the length of the audio track exactly matched the Blu-Ray video (there are separate YouTube videos for the Q&A anyway, see [Bonus: After-movie Q&A](#bonus-after-movie-qa) below).
- Added fade-in and fade-out audio effects to the beginning and end of the track.
- Exported a **lossless** FLAC file (check the [Reddit thread](https://www.reddit.com/r/movies/comments/4lwrt4/there_was_no_official_directors_commentary_for/) to find a link). This file format works well for remuxing and doesn't further degrade the audio quality.
	- For my personal remux, I exported the FLAC file with the least amount of compression (1.5 GB). Less compression = less CPU overhead for low-power TV boxes/transcoders to decompress.
	- For quicker file transfers, I used the maximum compression (790 MB). I know this is still a really big file and a pain to download, but I just could not stand the thought of further degrading the audio by using a **lossy** compression format to further reduce the size. If you want to convert this file to the least amount of compression like mine, open the file in Audacity and re-export it.

## Create the Final MKV file

I used [MakeMKV](http://www.makemkv.com/) to rip the Blu-Ray to an MKV file, and [MKVToolNix](https://mkvtoolnix.download/downloads.html) to mux in the new audio and subtitle tracks. 

This repo houses the SRT file. For the audio file, you can check the [Reddit thread](https://www.reddit.com/r/movies/comments/4lwrt4/there_was_no_official_directors_commentary_for/) to find a link.

## Bonus: After-movie Q&A

- Part 1: https://www.youtube.com/watch?v=qrk5q4iE00E
- Part 2: https://www.youtube.com/watch?v=IdJ8Gh46TSg
