# SrtPlayer

An Android SRT test player powered by [ExoPayer](https://github.com/google/ExoPlayer). Most of this code
comes from [YoussefHenna](https://github.com/YoussefHenna) reply in
the [SRT support ExoPayer issue](https://github.com/google/ExoPlayer/issues/8647).

It demonstrates how to use [srtdroid](https://github.com/ThibaultBee/srtdroid) and read data from a
remote SRT device.

It is only a demo project, it is not recommend to use it in production.

## Test

In order to test SrtPlayer, I had 1 tools running:

1. startup sls server
2. run shell 
   ```bash
    ffmpeg -f lavfi -re -i smptebars=duration=300:size=1280x720:rate=30 -f lavfi -re -i sine=frequency=1000:duration=60:sample_rate=44100 -pix_fmt yuv420p -c:v libx264 -b:v 1000k -g 30 -keyint_min 40 -profile:v baseline -preset veryfast -f mpegts "srt://192.168.1.102:9999?streamid=uplive.sls.com/live/srt1stream"
    ```

3. app setting:
    player url : srt://192.168.1.102:9999?streamid=live.sls.com/live/srt1stream

Then press play on the video player.

## Licence

    Copyright 2021 Thibault B.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.