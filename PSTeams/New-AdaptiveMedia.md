New-AdaptiveMedia
-----------------




### Synopsis
Displays a media player for audio or video content.



---


### Description

Displays a media player for audio or video content.



---


### Examples
#### EXAMPLE 1
```PowerShell
New-AdaptiveMedia -PosterUrl 'https://adaptivecards.io/content/poster-video.png' {
    New-AdaptiveMediaSource -Type "video/mp4" -Url "https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4"
    New-AdaptiveMediaSource -Type "video/mp4" -Url "https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4"
}
```



---


### Parameters
#### **Sources**

One or more sources of media to attempt to play.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|true    |1       |false        |



#### **PosterUrl**

URL of an image to display before playing






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **AlternateText**

Alternate text describing the audio or video.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **Spacing**

Controls the amount of spacing between this element and the preceding element.



Valid Values:

* None
* Small
* Default
* Medium
* Large
* ExtraLarge
* Padding






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |4       |false        |



#### **Separator**

Draw a separating line at the top of the element.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **HorizontalAlignment**

Controls the horizontal text alignment.



Valid Values:

* Left
* Center
* Right






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |5       |false        |



#### **Height**

Specifies the height of the element.



Valid Values:

* Stretch
* Automatic






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |6       |false        |



#### **Id**

A unique identifier associated with the item.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |7       |false        |



#### **Hidden**

If used this item will be removed from the visual tree.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
Media playback is currently not supported in Adaptive Cards in Teams. Adding it for sake of having.
May need to improve how it's handled.



---


### Syntax
```PowerShell
New-AdaptiveMedia [-Sources] <ScriptBlock> [[-PosterUrl] <String>] [[-AlternateText] <String>] [[-Spacing] <String>] [-Separator] [[-HorizontalAlignment] <String>] [[-Height] <String>] [[-Id] <String>] [-Hidden] [<CommonParameters>]
```
