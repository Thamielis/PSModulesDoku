Approve-CMScript
----------------




### Synopsis
Approve a PowerShell script in Configuration Manager.



---


### Description

Use this cmdlet to approve a Powershell script in Configuration Manager. These scripts are integrated and managed in Configuration Manager. You can't run a script on devices until it's approved. After you approve a script, to run it use the Invoke-CMScript (Invoke-CMScript.md)cmdlet.



By default, you can't approve scripts that you author.



For more information, see Create and run PowerShell scripts from the Configuration Manager console (/mem/configmgr/apps/deploy-use/create-deploy-scripts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Deny-CMScript](Deny-CMScript)



* [Get-CMScript](Get-CMScript)



* [Invoke-CMScript](Invoke-CMScript)



* [New-CMScript](New-CMScript)



* [Remove-CMScript](Remove-CMScript)



* [Set-CMScript](Set-CMScript)



* [Create and run PowerShell scripts from the Configuration Manager console](Create and run PowerShell scripts from the Configuration Manager console)





---


### Examples
#### Example 1: Approve a script by using the script ID
```PowerShell
Approve-CMScript -ScriptGuid "DF8E7546-FD66-4A3D-A129-53AF5AA54F80"
```

#### Example 2: Approve a script by using script object variable
```PowerShell
$ScriptObj = Get-CMScript -Id "DF8E7546-FD66-4A3D-A129-53AF5AA54F80"
Approve-CMScript -InputObject $ScriptObj
```

#### Example 3: Bulk approve all unapproved scripts
```PowerShell
$scripts = Get-CMScript -Fast | Where-Object { -not $_.ApprovalState }

$me = $env:userdomain + "\" + $env:username
foreach ( $script in $scripts ) {
  if ( $script.Author -ne $me ) {
    Approve-CMScript -InputObject $script
  }
}
```



---


### Parameters
#### **Comment**

Specifies a comment about the approval of the script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specify a script object to approve. To get this object, use the Get-CMScript (Get-CMScript.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ScriptGuid**

Specify the ID of the script to approve. The format is a standard GUID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Approve-CMScript [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Approve-CMScript [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -ScriptGuid <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
