Invoke-CMScript
---------------




### Synopsis
Run a PowerShell script in Configuration Manager.



---


### Description

Use this cmdlet to run a PowerShell script in Configuration Manager. These scripts are integrated and managed in Configuration Manager.



You can't run a script until it's approved. To approve scripts programmatically, use the Approve-CMScript (Approve-CMScript.md)cmdlet.



For more information, see Create and run PowerShell scripts from the Configuration Manager console (/mem/configmgr/apps/deploy-use/create-deploy-scripts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMScript](Approve-CMScript)



* [Deny-CMScript](Deny-CMScript)



* [Get-CMScript](Get-CMScript)



* [New-CMScript](New-CMScript)



* [Remove-CMScript](Remove-CMScript)



* [Set-CMScript](Set-CMScript)



* [Create and run PowerShell scripts from the Configuration Manager console](Create and run PowerShell scripts from the Configuration Manager console)





---


### Examples
#### Example 1: Run a script by using its ID
```PowerShell
Invoke-CMScript -ScriptGuid "DF8E7546-FD66-4A3D-A129-53AF5AA54F80"
```

#### Example 2: Run a script by using an object variable
```PowerShell
$ScriptObj = Get-CMScript -Id "DF8E7546-FD66-4A3D-A129-53AF5AA54F80"

Invoke-CMScript -InputObject $ScriptObj
```

#### Example 3: Pass parameters to the target script
```PowerShell
$parameters = @{
  "FolderName"="c:\test\test1"
  "FileName"="test2"
}

Invoke-CMScript -ScriptGuid $scriptGuid -Device (Get-CMDevice -Name $targetPCName) -ScriptParameter $parameters
```



---


### Parameters
#### **Collection**

Specify a collection object to run this script. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of a collection to run this script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specify the name of a collection to run this script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Device**

Specify an object for a device to run this script. To get this object, use the Get-CMDevice (Get-CMDevice.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases|
|-------------------|--------|--------|-------------|-------|
|`[IResultObject[]]`|false   |named   |False        |Devices|



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

Specify a script object to run. To get this object, use the Get-CMScript (Get-CMScript.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ScriptGuid**

Specify the ID of the script to run. The format is a standard GUID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptParameter**

Applies to version 2010 and later. Use this parameter to pass parameters to the target script. Specify a hashtable with the required parameters. For an example of usage, see Examples (#examples).






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Invoke-CMScript [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Device <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-ScriptParameter <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMScript [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-Device <IResultObject[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -ScriptGuid <String> [-ScriptParameter <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
