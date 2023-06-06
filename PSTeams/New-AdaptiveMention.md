New-AdaptiveMention
-------------------




### Synopsis
Allows Adaptive Card to mention specific person in the notification.



---


### Description

Allows Adaptive Card to mention specific person in the notification.
Currently Adaptive Card in incoming webhook notifications allows you to define a mention property, but it doesn't notify the user on notification.
It's supposed to be enabled in future by Microsoft.



---


### Examples
#### EXAMPLE 1
```PowerShell
przemyslaw.klys</at>' -UserPrincipalName 'przemyslaw.klys@evotec.test'
```

#### EXAMPLE 2
```PowerShell
New-AdaptiveMention -Text 'przemyslaw.klys' -UserPrincipalName 'przemyslaw.klys@evotec.test' -Name 'Przemysław Kłys'
```

#### EXAMPLE 3
```PowerShell
New-AdaptiveCard -Uri $URI -VerticalContentAlignment center {
    New-AdaptiveTextBlock -Size ExtraLarge -Weight Bolder -Text 'Test' -Color Attention -HorizontalAlignment Center
    New-AdaptiveColumnSet {
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Dark
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Light
        }
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Warning
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1' -Color Good
        }
        New-AdaptiveColumn {
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1 <at>Name</at>' -Color Warning
            New-AdaptiveTextBlock -Size 'Medium' -Text 'Test Card Title 1 <at>Zenon Jaskuła</at>' -Color Warning
        }
    }
    New-AdaptiveMention -Text 'Zenon Jaskuła' -UserPrincipalName 'przemyslaw.klys@evotec.test'
    New-AdaptiveMention -Text 'Name' -UserPrincipalName 'przemyslaw.klys@evotec.test'
} -Verbose -FullWidth
```



---


### Parameters
#### **Text**

Provide the text to be mentioned by using <at>person</at> tag. You can provide tags or skip them. Should work either way.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **UserPrincipalName**

Provide the user principal name of the person to be mentioned.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |2       |false        |



#### **Name**

Provide the name of the person to be mentioned. This is optional.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |3       |false        |





---


### Notes
More information here: https://github.com/EvotecIT/PSTeams/issues/17



---


### Syntax
```PowerShell
New-AdaptiveMention [-Text] <String> [-UserPrincipalName] <String> [[-Name] <String>] [<CommonParameters>]
```
