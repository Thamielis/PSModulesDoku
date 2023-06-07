Get-LansweeperReport
--------------------




### Synopsis

Get-LansweeperReport [-SqlInstance <string>] [-Database <string>] [-ListReports] [<CommonParameters>]

Get-LansweeperReport -Report <string[]> [-SqlInstance <string>] [-Database <string>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Database**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **ListReports**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Report**

Valid Values:

* AdobeJulySecurityUpdateVulnerabilityAudit
* AllInstalledWindowsSoftware
* AllServersTypes
* AllWorkstationsWithoutAntivirusSoftwareAudit
* AssetUptimeSinceLastRebootAudit
* BitLockerDriveEncryptionAudit
* ComputerProcessorInformation
* DellSupportAssistDLLHijackingVulnerabilityAudit
* Firefox68SecurityUpdateAudit
* InstalledWebBrowsers
* InstalledWindowsFeatures
* InstalledWindowsUpdates
* IntelProcessorDiagnosticToolVulnerabilityAudit
* LocalPrinters
* MicrosoftBlueKeepVulnerabilityAudit
* MicrosoftPatchTuesdayAuditJuly2019
* MicrosoftPatchTuesdayAuditJune2019
* MonitorInformation
* MultipleChrome75VulnerabilitiesAudit
* NonOEMWindowsLicense
* OEMWindowsLicense
* PrinterStatus
* PrinterTonerLevel
* ServerswithLessThan10%FreeDiskSpaceAudit
* SharedPrinters
* SoftwareLicenseKeyOverview
* UptimeAudit
* WindowsAutomaticUpdateSettingsAudit
* WindowsDiskSpaceAudit
* WindowsServerOverview
* WorkstationswithLessThan10%FreeDiskSpaceAudit






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|true    |Named   |false        |



#### **SqlInstance**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |





---


### Inputs
None




---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=Get-LansweeperReport; CommonParameters=True; parameter=System.Object[]}, @{name=Get-LansweeperReport; CommonParameters=True; parameter=System.Object[]}}
```
