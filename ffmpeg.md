Add audio to video
---
`ffmpeg -i video.ext -i audio.ext -codec copy output.ext`

option: `-shortest` Finish encoding when the shortest input stream ends.

source: [stackoverflow.com](https://stackoverflow.com/a/11783474)

Speeding up video
---
`ffmpeg -i input.ext -filter:v "setpts=0.5*PTS" -an output.mext`

option: `-an`	Disable audio

Formula to compute pts = 1 / (input length second / expected output second)

source: [ffmpeg.org](https://trac.ffmpeg.org/wiki/How%20to%20speed%20up%20/%20slow%20down%20a%20video)

Covert mp4 to mkv with subtitle
---
`ffmpeg -i input.mp4 -f srt -i subtitle.srt -c:v copy -c:a copy output.mkv`


Batch convert videos by ffmpeg
---
`for i in $(ls *iext); do ffmpeg -i $i -vcodec copy -acodec copy ${i%.iext}.oext; done;`
