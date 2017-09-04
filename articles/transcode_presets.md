---
title: "Transcode Presets"
layout: article
---

### Transcode Presets

<br/>

Blitline offers various different types of output transcoding. Below are the available types. If you need a custom preset, feel free to contact us and we can work with you to configure a specific output.

<br/>

**System preset generic 1080p**
--------------------------
- Description: System preset generic 1080p
- ID: 1351620000001-000001
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1920",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "1080",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "4"
    },
            "aspect_ratio" : "16:9",
                "bit_rate" : "5400",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**System preset generic 720p**
--------------------------
- Description: System preset generic 720p
- ID: 1351620000001-000010
- Output: mp4
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "2400",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**System preset generic 480p 16:9**
--------------------------
- Description: System preset generic 480p 16:9
- ID: 1351620000001-000020
- Output: mp4
- Max Height: 480
- Max Width: 854

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "854",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "480",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "1200",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**System preset generic 480p 4:3**
--------------------------
- Description: System preset generic 480p 4:3
- ID: 1351620000001-000030
- Output: mp4
- Max Height: 480
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "480",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3"
    },
                "bit_rate" : "900",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**System preset generic 360p 16:9**
--------------------------
- Description: System preset generic 360p 16:9
- ID: 1351620000001-000040
- Output: mp4
- Max Height: 360
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "360",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3"
    },
                "bit_rate" : "720",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**System preset generic 360p 4:3**
--------------------------
- Description: System preset generic 360p 4:3
- ID: 1351620000001-000050
- Output: mp4
- Max Height: 360
- Max Width: 480

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "480",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "360",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3"
    },
                "bit_rate" : "600",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**System preset generic 320x240**
--------------------------
- Description: System preset generic 320x240
- ID: 1351620000001-000061
- Output: mp4
- Max Height: 240
- Max Width: 320

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "320",
          "padding_policy" : "NoPad",
              "frame_rate" : "15",
              "max_height" : "240",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "1.3"
    },
                "bit_rate" : "300",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**iPhone 4s and above, iPad 3G and above, iPad mini, Samsung Galaxy S2/S3/Tab 2**
--------------------------
- Description: iPhone 4s and above, iPad 3G and above, iPad mini, Samsung Galaxy S2/S3/Tab 2
- ID: 1351620000001-100020
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1920",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "1080",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "4.1"
    },
                "bit_rate" : "5000",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**iPhone 1, 3, iPod classic**
--------------------------
- Description: iPhone 1, 3, iPod classic
- ID: 1351620000001-100040
- Output: mp4
- Max Height: 480
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "480",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3"
    },
                "bit_rate" : "1500",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Apple TV 2G**
--------------------------
- Description: Apple TV 2G
- ID: 1351620000001-100050
- Output: mp4
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "5000",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Apple TV 3G, Roku HD/2 XD**
--------------------------
- Description: Apple TV 3G, Roku HD/2 XD
- ID: 1351620000001-100060
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1920",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "1080",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "4"
    },
                "bit_rate" : "5000",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Facebook, SmugMug, Vimeo, YouTube**
--------------------------
- Description: Facebook, SmugMug, Vimeo, YouTube
- ID: 1351620000001-100070
- Output: mp4
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "2200",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Kindle Fire HD**
--------------------------
- Description: Kindle Fire HD
- ID: 1351620000001-100080
- Output: mp4
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "4"
    },
                "bit_rate" : "2200",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Kindle Fire HD 8.9**
--------------------------
- Description: Kindle Fire HD 8.9
- ID: 1351620000001-100090
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1920",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "1080",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "4"
    },
                "bit_rate" : "5400",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Kindle Fire HDX, Kindle Fire HDX 8.9**
--------------------------
- Description: Kindle Fire HDX, Kindle Fire HDX 8.9
- ID: 1351620000001-100150
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1920",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "1080",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "4.1"
    },
                "bit_rate" : "5000",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**NTSC - MPG**
--------------------------
- Description: NTSC - MPG
- ID: 1351620000001-100160
- Output: mpg
- Max Height: 480
- Max Width: 720

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFill",
               "max_width" : "720",
          "padding_policy" : "Pad",
              "frame_rate" : "29.97",
              "max_height" : "480",
      "keyframes_max_dist" : "15",
               "fixed_gop" : "true",
                   "codec" : "mpeg2",
           "codec_options" : {
                 "chroma_subsampling" : "yuv420p",
                       "max_bit_rate" : "6500",
        "color_space_conversion_mode" : "Auto",
                        "buffer_size" : "65000",
                    "interlaced_mode" : "TopFirst"
    },
                "bit_rate" : "6500",
    "display_aspect_ratio" : "16:9"
}

{% endhighlight %}

<br/>

**PAL - MPG**
--------------------------
- Description: PAL - MPG
- ID: 1351620000001-100170
- Output: mpg
- Max Height: 576
- Max Width: 720

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFill",
               "max_width" : "720",
          "padding_policy" : "Pad",
              "frame_rate" : "25",
              "max_height" : "576",
      "keyframes_max_dist" : "12",
               "fixed_gop" : "true",
                   "codec" : "mpeg2",
           "codec_options" : {
                 "chroma_subsampling" : "yuv420p",
                       "max_bit_rate" : "6500",
        "color_space_conversion_mode" : "Auto",
                        "buffer_size" : "65000",
                    "interlaced_mode" : "TopFirst"
    },
                "bit_rate" : "6500",
    "display_aspect_ratio" : "16:9"
}

{% endhighlight %}

<br/>

**Full HD 1080i60 - MP4**
--------------------------
- Description: Full HD 1080i60 - MP4
- ID: 1351620000001-100180
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFill",
               "max_width" : "1920",
          "padding_policy" : "Pad",
              "frame_rate" : "29.97",
              "max_height" : "1080",
      "keyframes_max_dist" : "15",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "10000",
                    "interlaced_mode" : "TopFirst",
                              "level" : "4.1",
        "color_space_conversion_mode" : "Auto",
               "max_reference_frames" : "3",
                        "buffer_size" : "100000"
    },
                "bit_rate" : "10000",
    "display_aspect_ratio" : "16:9"
}

{% endhighlight %}

<br/>

**Full HD 1080i50 - MP4**
--------------------------
- Description: Full HD 1080i50 - MP4
- ID: 1351620000001-100190
- Output: mp4
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFill",
               "max_width" : "1920",
          "padding_policy" : "Pad",
              "frame_rate" : "25",
              "max_height" : "1080",
      "keyframes_max_dist" : "12",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "10000",
                    "interlaced_mode" : "TopFirst",
                              "level" : "4.1",
        "color_space_conversion_mode" : "Auto",
               "max_reference_frames" : "3",
                        "buffer_size" : "100000"
    },
                "bit_rate" : "10000",
    "display_aspect_ratio" : "16:9"
}

{% endhighlight %}

<br/>

**Gif (Animated)**
--------------------------
- Description: Gif (Animated)
- ID: 1351620000001-100200
- Output: gif
- Max Height: auto
- Max Width: auto

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "auto",
          "padding_policy" : "NoPad",
              "frame_rate" : "15",
              "max_height" : "auto",
                   "codec" : "gif",
           "codec_options" : {
        "loop_count" : "Infinite"
    },
                "bit_rate" : "400",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Web: Flash Video**
--------------------------
- Description: Web: Flash Video
- ID: 1351620000001-100210
- Output: flv
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "2200",
                    "interlaced_mode" : "TopFirst",
                              "level" : "3.1",
        "color_space_conversion_mode" : "Auto",
               "max_reference_frames" : "3",
                        "buffer_size" : "22000"
    },
                "bit_rate" : "2200",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Full HD 1080i60 - XDCAM422**
--------------------------
- Description: Full HD 1080i60 - XDCAM422
- ID: 1351620000001-100220
- Output: mxf
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFill",
               "max_width" : "1920",
          "padding_policy" : "Pad",
              "frame_rate" : "29.97",
              "max_height" : "1080",
      "keyframes_max_dist" : "15",
               "fixed_gop" : "true",
                   "codec" : "mpeg2",
           "codec_options" : {
                 "chroma_subsampling" : "yuv422p",
                       "max_bit_rate" : "50000",
        "color_space_conversion_mode" : "Auto",
                        "buffer_size" : "100000",
                    "interlaced_mode" : "TopFirst"
    },
                "bit_rate" : "50000",
    "display_aspect_ratio" : "16:9"
}

{% endhighlight %}

<br/>

**Full HD 1080i50 - XDCAM422**
--------------------------
- Description: Full HD 1080i50 - XDCAM422
- ID: 1351620000001-100230
- Output: mxf
- Max Height: 1080
- Max Width: 1920

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFill",
               "max_width" : "1920",
          "padding_policy" : "Pad",
              "frame_rate" : "25",
              "max_height" : "1080",
      "keyframes_max_dist" : "12",
               "fixed_gop" : "true",
                   "codec" : "mpeg2",
           "codec_options" : {
                 "chroma_subsampling" : "yuv422p",
                       "max_bit_rate" : "50000",
        "color_space_conversion_mode" : "Auto",
                        "buffer_size" : "100000",
                    "interlaced_mode" : "TopFirst"
    },
                "bit_rate" : "50000",
    "display_aspect_ratio" : "16:9"
}

{% endhighlight %}

<br/>

**Webm 720p**
--------------------------
- Description: Webm 720p
- ID: 1351620000001-100240
- Output: webm
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "29.97",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "vp8",
           "codec_options" : {
        "profile" : "0"
    },
                "bit_rate" : "2400",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Webm VP9 720p**
--------------------------
- Description: Webm VP9 720p
- ID: 1351620000001-100250
- Output: webm
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "vp9",
           "codec_options" : {},
                "bit_rate" : "1200",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Webm VP9 360p**
--------------------------
- Description: Webm VP9 360p
- ID: 1351620000001-100260
- Output: webm
- Max Height: 360
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "360",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "false",
                   "codec" : "vp9",
           "codec_options" : {},
                "bit_rate" : "600",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS 2M**
--------------------------
- Description: HLS 2M
- ID: 1351620000001-200010
- Output: ts
- Max Height: 768
- Max Width: 1024

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1024",
          "padding_policy" : "NoPad",
              "frame_rate" : "auto",
              "max_height" : "768",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "1872",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS Video - 2M**
--------------------------
- Description: HLS Video - 2M
- ID: 1351620000001-200015
- Output: ts
- Max Height: 768
- Max Width: 1024

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1024",
          "padding_policy" : "NoPad",
          "max_frame_rate" : "60",
              "frame_rate" : "auto",
              "max_height" : "768",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "1872",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "16848"
    },
                "bit_rate" : "1872",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS 1.5M**
--------------------------
- Description: HLS 1.5M
- ID: 1351620000001-200020
- Output: ts
- Max Height: 640
- Max Width: 960

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "960",
          "padding_policy" : "NoPad",
              "frame_rate" : "auto",
              "max_height" : "640",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "1372",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS Video - 1.5M**
--------------------------
- Description: HLS Video - 1.5M
- ID: 1351620000001-200025
- Output: ts
- Max Height: 640
- Max Width: 960

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "960",
          "padding_policy" : "NoPad",
          "max_frame_rate" : "60",
              "frame_rate" : "auto",
              "max_height" : "640",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "1372",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "12348"
    },
                "bit_rate" : "1372",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS 1M**
--------------------------
- Description: HLS 1M
- ID: 1351620000001-200030
- Output: ts
- Max Height: 432
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
              "frame_rate" : "auto",
              "max_height" : "432",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1"
    },
                "bit_rate" : "872",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS Video - 1M**
--------------------------
- Description: HLS Video - 1M
- ID: 1351620000001-200035
- Output: ts
- Max Height: 432
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
          "max_frame_rate" : "60",
              "frame_rate" : "auto",
              "max_height" : "432",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "872",
                    "interlaced_mode" : "Progressive",
                              "level" : "3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "7848"
    },
                "bit_rate" : "872",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS 600k**
--------------------------
- Description: HLS 600k
- ID: 1351620000001-200040
- Output: ts
- Max Height: 320
- Max Width: 480

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "480",
          "padding_policy" : "NoPad",
              "frame_rate" : "auto",
              "max_height" : "320",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "3",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3"
    },
                "bit_rate" : "472",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS Video - 600k**
--------------------------
- Description: HLS Video - 600k
- ID: 1351620000001-200045
- Output: ts
- Max Height: 320
- Max Width: 480

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "480",
          "padding_policy" : "NoPad",
          "max_frame_rate" : "60",
              "frame_rate" : "auto",
              "max_height" : "320",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
                       "max_bit_rate" : "472",
                    "interlaced_mode" : "Progressive",
                              "level" : "3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "4248"
    },
                "bit_rate" : "472",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS 400k**
--------------------------
- Description: HLS 400k
- ID: 1351620000001-200050
- Output: ts
- Max Height: 288
- Max Width: 400

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "400",
          "padding_policy" : "NoPad",
              "frame_rate" : "auto",
              "max_height" : "288",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
               "max_reference_frames" : "1",
        "color_space_conversion_mode" : "None",
                    "interlaced_mode" : "Progressive",
                              "level" : "3"
    },
                "bit_rate" : "272",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**HLS Video - 400k**
--------------------------
- Description: HLS Video - 400k
- ID: 1351620000001-200055
- Output: ts
- Max Height: 288
- Max Width: 400

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "400",
          "padding_policy" : "NoPad",
          "max_frame_rate" : "60",
              "frame_rate" : "auto",
              "max_height" : "288",
      "keyframes_max_dist" : "90",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "baseline",
                       "max_bit_rate" : "272",
                    "interlaced_mode" : "Progressive",
                              "level" : "3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "1",
                        "buffer_size" : "2448"
    },
                "bit_rate" : "272",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 3M**
--------------------------
- Description: Smooth 3M
- ID: 1351620000001-400010
- Output: fmp4
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "2962",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "17772"
    },
                "bit_rate" : "2962",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 2M**
--------------------------
- Description: Smooth 2M
- ID: 1351620000001-400020
- Output: fmp4
- Max Height: 560
- Max Width: 992

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "992",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "560",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "2056",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "12336"
    },
                "bit_rate" : "2056",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 1.5M**
--------------------------
- Description: Smooth 1.5M
- ID: 1351620000001-400030
- Output: fmp4
- Max Height: 432
- Max Width: 768

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "768",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "432",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "1427",
                    "interlaced_mode" : "Progressive",
                              "level" : "3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "8562"
    },
                "bit_rate" : "1427",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 1M**
--------------------------
- Description: Smooth 1M
- ID: 1351620000001-400040
- Output: fmp4
- Max Height: 332
- Max Width: 592

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "592",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "332",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "991",
                    "interlaced_mode" : "Progressive",
                              "level" : "2.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "5946"
    },
                "bit_rate" : "991",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 800k**
--------------------------
- Description: Smooth 800k
- ID: 1351620000001-400050
- Output: fmp4
- Max Height: 252
- Max Width: 448

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "448",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "252",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "688",
                    "interlaced_mode" : "Progressive",
                              "level" : "2.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "4128"
    },
                "bit_rate" : "688",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 600k**
--------------------------
- Description: Smooth 600k
- ID: 1351620000001-400060
- Output: fmp4
- Max Height: 208
- Max Width: 368

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "368",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "208",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "477",
                    "interlaced_mode" : "Progressive",
                              "level" : "1.3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "2862"
    },
                "bit_rate" : "477",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 500k**
--------------------------
- Description: Smooth 500k
- ID: 1351620000001-400070
- Output: fmp4
- Max Height: 160
- Max Width: 284

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "284",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "160",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "331",
                    "interlaced_mode" : "Progressive",
                              "level" : "1.3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "1986"
    },
                "bit_rate" : "331",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**Smooth 400k**
--------------------------
- Description: Smooth 400k
- ID: 1351620000001-400080
- Output: fmp4
- Max Height: 128
- Max Width: 224

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "224",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "128",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "high",
                       "max_bit_rate" : "230",
                    "interlaced_mode" : "Progressive",
                              "level" : "1.3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "1380"
    },
                "bit_rate" : "230",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**MPEG-Dash Video - 4.8M**
--------------------------
- Description: MPEG-Dash Video - 4.8M
- ID: 1351620000001-500020
- Output: fmp4
- Max Height: 720
- Max Width: 1280

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "1280",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "720",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "4800",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "9600"
    },
                "bit_rate" : "4800",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**MPEG-Dash Video - 2.4M**
--------------------------
- Description: MPEG-Dash Video - 2.4M
- ID: 1351620000001-500030
- Output: fmp4
- Max Height: 480
- Max Width: 854

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "854",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "480",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "2400",
                    "interlaced_mode" : "Progressive",
                              "level" : "3.1",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "4800"
    },
                "bit_rate" : "2400",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**MPEG-Dash Video - 1.2M**
--------------------------
- Description: MPEG-Dash Video - 1.2M
- ID: 1351620000001-500040
- Output: fmp4
- Max Height: 360
- Max Width: 640

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "640",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "360",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "1200",
                    "interlaced_mode" : "Progressive",
                              "level" : "3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "3",
                        "buffer_size" : "2400"
    },
                "bit_rate" : "1200",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>

**MPEG-Dash Video - 600k**
--------------------------
- Description: MPEG-Dash Video - 600k
- ID: 1351620000001-500050
- Output: fmp4
- Max Height: 240
- Max Width: 426

{% highlight json %}

{
           "sizing_policy" : "ShrinkToFit",
               "max_width" : "426",
          "padding_policy" : "NoPad",
              "frame_rate" : "30",
              "max_height" : "240",
      "keyframes_max_dist" : "60",
               "fixed_gop" : "true",
                   "codec" : "H.264",
           "codec_options" : {
                            "profile" : "main",
                       "max_bit_rate" : "600",
                    "interlaced_mode" : "Progressive",
                              "level" : "3",
        "color_space_conversion_mode" : "None",
               "max_reference_frames" : "1",
                        "buffer_size" : "1200"
    },
                "bit_rate" : "600",
    "display_aspect_ratio" : "auto"
}

{% endhighlight %}

<br/>
