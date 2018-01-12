---
UID: NC:d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
title: DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO
author: windows-driver-content
description: The pfnCreateNewModeInfo function returns a pointer to a D3DKMDT_MONITOR_SOURCE_MODE structure that the display miniport driver populates before calling pfnAddMode.
old-location: display\dxgk_monitorsourcemodeset_interface_pfncreatenewmodeinfo.htm
old-project: display
ms.assetid: 314b345c-a40b-418d-a2d8-c7b42e5fd27d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnCreateNewModeInfo
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO callback



## -description
The <b>pfnCreateNewModeInfo</b> function returns a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_source_mode.md">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that the display miniport driver populates before calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode.md">pfnAddMode</a>.



## -prototype

````
DXGKDDI_MONITORSOURCEMODESET_CREATENEWMODEINFO pfnCreateNewModeInfo;

NTSTATUS APIENTRY pfnCreateNewModeInfo(
  _In_  const D3DKMDT_HMONITORSOURCEMODESET hMonitorSourceModeSet,
  _Out_       D3DKMDT_MONITOR_SOURCE_MODE   **ppNewMonitorSourceModeInfo
)
{ ... }
````


## -parameters

### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param ppNewMonitorSourceModeInfo [out]

[out] A pointer to a variable that receives a pointer to a newly created D3DKMDT_MONITOR_SOURCE_MODE structure allocated by the VidPN manager.


## -returns
The <b>pfnCreateNewModeInfo</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The function failed because it was unable to allocate enough memory.

 


## -remarks
After you call <b>pfnCreateNewModeInfo</b> to obtain a D3DKMDT_MONITOR SOURCE_MODE structure, you must do one, but not both, of the following:

Populate the structure and pass it to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_addmode.md">pfnAddMode</a>.

Release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_releasemodeinfo.md">pfnReleaseModeInfo</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>