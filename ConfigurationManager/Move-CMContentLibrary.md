Move-CMContentLibrary
---------------------




### Synopsis
Move the content library before adding a passive site.



---


### Description

Use this cmdlet to move the content library. To configure site server high availability or to free up hard drive space on your central administration or primary site servers, relocate the content library to another storage location. For more information, see Configure a remote content library for the site server (/mem/configmgr/core/plan-design/hierarchy/remote-content-library).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSite](Get-CMSite)



* [Configure a remote content library for the site server](Configure a remote content library for the site server)





---


### Examples
#### Example 1: Move the content library for a site object
```PowerShell
Move-CMContentLibrary -InputObject $Site -NewLocation $NewLocationPath
```

#### Example 2: Move the content library for a site code
```PowerShell
Move-CMContentLibrary -SiteCode $SiteCode -NewLocation $NewLocationPath
```



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

Specify a site object. To get this object, use the Get-CMSite (Get-CMSite.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Site   |



#### **NewLocation**

Specify the network path to the new location for the content library.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specify the site code.






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
Move-CMContentLibrary [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -NewLocation <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Move-CMContentLibrary [-DisableWildcardHandling] [-ForceWildcardHandling] -NewLocation <String> -SiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
