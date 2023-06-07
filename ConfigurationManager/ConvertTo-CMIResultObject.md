ConvertTo-CMIResultObject
-------------------------




### Synopsis
Converts a ManagementBaseObject to an IResultObject .



---


### Description

The ConvertTo-CMIResultObject cmdlet converts a ManagementBaseObject to an IResultObject .



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [ConvertFrom-CMIResultObject](ConvertFrom-CMIResultObject)





---


### Examples
#### Example 1: Convert a ManagementBaseObject to an IResultObject by passing a WMI object through the pipeline
```PowerShell
PS ABC:\> $WmiObject = Get-WmiObject -Query "SELECT * FROM SMS_Site" -Namespace "root\sms\site_PS1"
PS ABC:\> $WmiObject | ConvertTo-CMIResultObject
```
The first command gets the site object with the code of PS1 and stores the object in the $WmiObject variable.


The second command uses the pipeline operator to pass the site object stored in $WmiObject to ConvertTo-CMIResultObject , which converts the site object to an IResultObject .
#### Example 2: Convert a ManagementBaseObject to an IResultObject by getting a WMI object
```PowerShell
PS ABC:\> $WmiObject = Get-WmiObject -Query "SELECT * FROM SMS_Site" -Namespace "root\sms\site_PS1"
PS ABC:\> ConvertTo-CMIResultObject -InputObject $WmiObject
```
The first command gets the site object with the code of PS1 and stores the object in the $WmiObject variable.


The second command converts the site object stored in $WmiObject to an IResultObject .


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the ManagementBaseObject to convert to an IResultObject .






|Type                    |Required|Position|PipelineInput |
|------------------------|--------|--------|--------------|
|`[ManagementBaseObject]`|true    |named   |True (ByValue)|





---


### Inputs
System.Management.ManagementBaseObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
ConvertTo-CMIResultObject [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <ManagementBaseObject> [<CommonParameters>]
```
