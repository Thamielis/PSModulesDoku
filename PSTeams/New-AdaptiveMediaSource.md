New-AdaptiveMediaSource
-----------------------




### Synopsis
Defines a source for a Media element



---


### Description

Defines a source for a Media element



---


### Examples
#### EXAMPLE 1
```PowerShell
New-AdaptiveMediaSource -Type "video/mp4" -Url "https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4"
```

#### EXAMPLE 2
```PowerShell
New-AdaptiveMedia -PosterUrl 'https://adaptivecards.io/content/poster-video.png' {
    New-AdaptiveMediaSource -Type "video/mp4" -Url "https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4"
    New-AdaptiveMediaSource -Type "video/mp4" -Url "https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4"
}
```



---


### Parameters
#### **Type**

Mime type of associated media (e.g. "video/mp4").






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |1       |false        |



#### **Url**

URL to media.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |





---


### Notes
Media playback is currently not supported in Adaptive Cards in Teams. Adding it for sake of having.
May need to improve how it's handled.



---


### Syntax
```PowerShell
New-AdaptiveMediaSource [[-Type] <String>] [[-Url] <String>] [<CommonParameters>]
```
