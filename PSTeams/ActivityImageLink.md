New-TeamsActivityImage
----------------------




### Synopsis
Adds ability to add an image to an activity within Office 365 Connector Card



---


### Description

Adds ability to add an image to an activity within Office 365 Connector Card



---


### Examples
#### EXAMPLE 1
```PowerShell
Send-TeamsMessage -URI $TeamsID -MessageTitle 'PSTeams - Pester Test' -MessageText "This text will show up" -Color DodgerBlue {
    New-TeamsSection {
        New-TeamsActivityTitle -Title "**PSTeams**"
        New-TeamsActivitySubtitle -Subtitle "@PSTeams - $CurrentDate"
        New-TeamsActivityImage -Image Add
        New-TeamsActivityText -Text "This message proves PSTeams Pester test passed properly."
        New-TeamsFact -Name 'PS Version' -Value "**$($PSVersionTable.PSVersion)**"
        New-TeamsFact -Name 'PS Edition' -Value "**$($PSVersionTable.PSEdition)**"
        New-TeamsFact -Name 'OS' -Value "**$($PSVersionTable.OS)**"
        New-TeamsButton -Name 'Visit English Evotec Website' -Link "https://evotec.xyz"
    }
} -Verbose
```



---


### Parameters
#### **Image**

Choose one of built-in images to display. Options are: 'Add', 'Alert', 'Cancel', 'Check', 'Disable', 'Download', 'Info', 'Minus', 'Question', 'Reload', 'None'



Valid Values:

* Add
* Alert
* Cancel
* Check
* Disable
* Download
* Info
* Minus
* Question
* Reload
* None






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Link**

Provide a link to image to display in the card.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **Path**

Provide a path to image to display in the card. JPG and PNG files are supported.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[FileInfo]`|false   |named   |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
New-TeamsActivityImage [-Link <String>] [<CommonParameters>]
```
```PowerShell
New-TeamsActivityImage [-Image <String>] [<CommonParameters>]
```
```PowerShell
New-TeamsActivityImage [-Path <FileInfo>] [<CommonParameters>]
```
