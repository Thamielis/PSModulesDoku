New-HeroCard
------------




### Synopsis
Provides a quick and easy way to build a Hero Card and send it thru incoming webhook to Microsoft Teams.



---


### Description

Provides a quick and easy way to build a Hero Card and send it thru incoming webhook to Microsoft Teams.



---


### Examples
#### EXAMPLE 1
```PowerShell
New-HeroCard -Title 'Seattle Center Monorail' -SubTitle 'Seattle Center Monorail' -Text "The Seattle Center Monorail is an elevated train line between Seattle Center (near the Space Needle) and downtown Seattle. It was built for the 1962 World's Fair. Its original two trains, completed in 1961, are still in service." {
    New-HeroImage -Url 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/49/Seattle_monorail01_2008-02-25.jpg/1024px-Seattle_monorail01_2008-02-25.jpg'
    New-HeroButton -Type openUrl -Title 'Official website' -Value 'https://www.seattlemonorail.com'
    New-HeroButton -Type openUrl -Title 'Wikipeda page' -Value 'https://www.seattlemonorail.com'
    New-HeroButton -Type imBack -Title 'Evotec page' -Value 'https://www.evotec.xyz'
} -Uri $URI
```



---


### Parameters
#### **Content**

ScriptBlock to define the content of HeroCard






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|true    |1       |false        |



#### **Title**

Title of the hero card






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **SubTitle**

Subtitle of the hero card






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |



#### **Text**

Text to display within hero card






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |4       |false        |



#### **Uri**

URI/URL of Incoming Webhook generated in Microsoft Teams






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |5       |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
New-HeroCard [-Content] <ScriptBlock> [[-Title] <String>] [[-SubTitle] <String>] [[-Text] <String>] [[-Uri] <String>] [<CommonParameters>]
```
