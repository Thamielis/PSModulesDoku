Set-DesktopWallpaper
--------------------




### Synopsis

Set-DesktopWallpaper [-Index <int>] [-WallpaperPath <string>] [-Position <DesktopWallpaperPosition>] [<CommonParameters>]

Set-DesktopWallpaper [-MonitorID <string>] [-WallpaperPath <string>] [-Position <DesktopWallpaperPosition>] [<CommonParameters>]

Set-DesktopWallpaper [-All] [-WallpaperPath <string>] [-Position <DesktopWallpaperPosition>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **All**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **Index**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |Named   |false        |



#### **MonitorID**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **Position**

Valid Values:

* Center
* Tile
* Stretch
* Fit
* Fill
* Span






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[DesktopWallpaperPosition]`|false   |Named   |false        |



#### **WallpaperPath**




|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[string]`|false   |Named   |false        |FilePath|





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
{@{name=Set-DesktopWallpaper; CommonParameters=True; parameter=System.Object[]}, @{name=Set-DesktopWallpaper; CommonParameters=True; parameter=System.Object[]}, @{name=Set-Deskto…
```
