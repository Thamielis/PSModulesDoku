Get-CMComponentStatusMessage
----------------------------




### Synopsis
Get component status messages in Configuration Manager.



---


### Description

The Get-CMComponentStatusMessage cmdlet gets component status messages for a specified period.



Configuration Manager indicates whether operations succeed or fail and include other information in component status messages. Threads or processes send component status messages to Configuration Manager sites, which are identified by site codes.



You can define which messages to get by the severity of the message, the component that created the message, the computer that hosts that component, or the Configuration Manager server that receives the message. Always specify a viewing period as a TimeSpan object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMComponentStatusSetting](Get-CMComponentStatusSetting)



* [Get-CMSiteComponent](Get-CMSiteComponent)





---


### Examples
#### Example 1: Get error messages for a site
```PowerShell
Get-CMComponentStatusMessage -StartTime "2/1/2013 12:00 AM" -Severity Error
```

#### Example 2: Get warning messages for a site within the last 24 hours
```PowerShell
Get-CMComponentStatusMessage -StartTime $(Get-Date).AddHours(-24) -Severity Warning -SiteCode "CM1"
```

#### Example 3: Get summary of messages for all components within last 24 hours
```PowerShell
PS OPC:\> Get-CMSiteComponent | Select-Object -ExpandProperty ComponentName -Unique | Sort-Object ComponentName | ForEach-Object {
    $errs  = $(Get-CMComponentStatusMessage -ComponentName $_ -Severity Error -StartTime $(Get-Date).AddHours(-24)).Count
    $warns = $(Get-CMComponentStatusMessage -ComponentName $_ -Severity Warning -StartTime $(Get-Date).AddHours(-24)).Count
    [pscustomobject]@{
        Component  = $_
        Errors     = $errs
        Warnings   = $warns
    }
}

Component                             Errors Warnings
---------                             ------ --------
SMS_AD_SECURITY_GROUP_DISCOVERY_AGENT    742        0
SMS_WSUS_SYNC_MANAGER                     90        0
SMS_WSUS_CONFIGURATION_MANAGER             0        0
SMS_WSUS_CONTROL_MANAGER                  62        0
SMS_AD_SYSTEM_DISCOVERY_AGENT              0        0
SMS_CLIENT_HEALTH                          0        0
SMS_CLOUD_PROXYCONNECTOR                   0        0
SMS_AD_USER_DISCOVERY_AGENT                0      612
...
```



---


### Parameters
#### **ComponentName**

Specifies the name of a thread or process. A thread or process sends a component status message.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |Component|



#### **ComputerName**

Scope the status messages results and specify the name of a computer that hosts a component.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |MachineName|



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



#### **Severity**

Specifies the severity of component status messages to get.


> [!NOTE] > This parameter currently doesn't work with the `All` value, but also doesn't return any values if omitted.



Valid Values:

* All
* Error
* Warning
* Information






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Severity]`|false   |named   |False        |



#### **SiteCode**

Specifies a site code from which to get component status messages.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StartTime**

Specify a time for the start of the viewing period for the component status messages.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[DateTime]`|true    |named   |False        |ViewingPeriod|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_StatusMessage


* IResultObject#SMS_StatusMessage






---


### Notes




---


### Syntax
```PowerShell
Get-CMComponentStatusMessage [-ComponentName <String>] [-ComputerName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Severity {All | Error | Warning | Information}] [-SiteCode <String>] -StartTime <DateTime> [<CommonParameters>]
```
