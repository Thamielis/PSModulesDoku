Set-CMThirdPartyUpdateCatalog
-----------------------------




### Synopsis
Modify a third-party updates catalog.



---


### Description

Use this cmdlet to modify a third-party updates catalog. For more information, see Enable third-party updates (/mem/configmgr/sum/deploy-use/third-party-software-updates).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMThirdPartyUpdateCatalog](Get-CMThirdPartyUpdateCatalog)



* [New-CMThirdPartyUpdateCatalog](New-CMThirdPartyUpdateCatalog)



* [Remove-CMThirdPartyUpdateCatalog](Remove-CMThirdPartyUpdateCatalog)



* [Publish-CMThirdPartySoftwareUpdateContent](Publish-CMThirdPartySoftwareUpdateContent)



* [Get-CMThirdPartyUpdateCategory](Get-CMThirdPartyUpdateCategory)



* [Set-CMThirdPartyUpdateCategory](Set-CMThirdPartyUpdateCategory)



* [Enable third-party software updates](Enable third-party software updates)





---


### Examples
#### Example 1: Rename a third-party update catalog
```PowerShell
Set-CMThirdPartyUpdateCatalog -Name "Contoso updates" -NewName "Contoso update catalog"
```

#### Example 2: Change the description
```PowerShell
Set-CMThirdPartyUpdateCatalog -ThirdPartyUpdateCatalog $catalog -Description "All of the current Contoso hardware updates"
```

#### Example 3: Change support information
```PowerShell
$catalog | Set-CMThirdPartyUpdateCatalog -SupportContact "Contoso hardware support" -SupportUrl "https://hardware.contoso.com"
```

#### Example 4: Set the category publishing options for a v3 catalog
```PowerShell
$id = "5768207d-6c40-465b-ad65-50501661368f"
$option = [Microsoft.ConfigurationManagement.Cmdlets.Sum.Commands.PublishOptionType]::MetadataOnly
$idOptionPair = @{$id = $option}
Set-CMThirdPartyUpdateCatalog -CatalogName 'pmp' -CategoryIdPublishOption $idOptionPair -Subscribe -Force

$name = "2BrightSparks"
$name1 = "8x8, Inc."
$option = [Microsoft.ConfigurationManagement.Cmdlets.Sum.Commands.PublishOptionType]::MetadataOnly
$nameOptionPair = @{$name = $option; $name1 = $option}
Set-CMThirdPartyUpdateCatalog -CatalogName 'pmp' -CategoryNamePublishOption $nameOptionPair -Subscribe -Force
```



---


### Parameters
#### **CategoryIdPublishOption**

Set the category ID publish option when you subscribe to a v3 catalog.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **CategoryNamePublishOption**

Set the category name publish option when you subscribe to a v3 catalog.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **Description**

Specify the description for the third-party updates catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the third-party updates catalog to change.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |0       |False        |CatalogId|



#### **InputObject**

Specify an object for the third-party updates catalog to change. To get this object, use the Get-CMThirdPartyUpdateCatalog (Get-CMThirdPartyUpdateCatalog.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                |
|-----------------|--------|--------|--------------|-----------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|ThirdPartyUpdateCatalog|



#### **Name**

Specify the name of the third-party updates catalog to change.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |0       |False        |CatalogName|



#### **NewName**

Rename the selected third-party updates catalog.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |NewCatalogName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PublisherName**

Change the publisher name for the specified third-party updates catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Schedule**

Specify a schedule object to apply to the specified third-party updates catalog. Custom schedules override the default synchronization schedule, and are only available for subscribed catalogs.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **Subscribe**

Configure the site to subscribe to the third-party updates catalog. This parameter is the same as the console action to Subscribe to Catalog .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SupportContact**

Change the support contact for the specified third-party updates catalog.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SupportUrl**

Change the support URL for the specified third-party updates catalog.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|false   |named   |False        |



#### **SyncNow**

Trigger the site to synchronize the specified third-party updates catalog. This parameter is the same as the console action to Sync now .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Unsubscribe**

Configure the site to unsubscribe from the third-party updates catalog. This parameter is the same as the console action to Unsubscribe from Catalog .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_ISVCatalogs






---


### Notes
This cmdlet returns an object of the SMS_ISVCatalogs WMI class.



---


### Syntax
```PowerShell
Set-CMThirdPartyUpdateCatalog [-Id] <String> [-CategoryIdPublishOption <Hashtable>] [-CategoryNamePublishOption <Hashtable>] [-Description <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-PublisherName <String>] [-Schedule <IResultObject>] [-Subscribe] [-SupportContact <String>] [-SupportUrl <Uri>] [-SyncNow] [-Unsubscribe] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMThirdPartyUpdateCatalog [-InputObject] <IResultObject> [-CategoryIdPublishOption <Hashtable>] [-CategoryNamePublishOption <Hashtable>] [-Description <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-PublisherName <String>] [-Schedule <IResultObject>] [-Subscribe] [-SupportContact <String>] [-SupportUrl <Uri>] [-SyncNow] [-Unsubscribe] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMThirdPartyUpdateCatalog [[-Name] <String>] [-CategoryIdPublishOption <Hashtable>] [-CategoryNamePublishOption <Hashtable>] [-Description <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-PublisherName <String>] [-Schedule <IResultObject>] [-Subscribe] [-SupportContact <String>] [-SupportUrl <Uri>] [-SyncNow] [-Unsubscribe] [-Confirm] [-WhatIf] [<CommonParameters>]
```
