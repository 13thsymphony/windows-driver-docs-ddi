---
UID: NC.d3dkmddi.DXGKDDI_MONITORSOURCEMODESET_ADDMODE
title: DXGKDDI_MONITORSOURCEMODESET_ADDMODE
author: windows-driver-content
description: The pfnAddMode function adds a monitor source mode to a specified monitor source mode set object.
old-location: display\dxgk_monitorsourcemodeset_interface_pfnaddmode.htm
old-project: display
ms.assetid: 88fe5a2d-d140-4ebc-846d-acea39b8bc73
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: pfnAddMode
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
---

# DXGKDDI_MONITORSOURCEMODESET_ADDMODE callback



## -description
The <b>pfnAddMode</b> function adds a monitor source mode to a specified monitor source mode set object.


## -prototype

````
DXGKDDI_MONITORSOURCEMODESET_ADDMODE pfnAddMode;

NTSTATUS APIENTRY pfnAddMode(
  _In_ const D3DKMDT_HMONITORSOURCEMODESET     hMonitorSourceModeSet,
  _In_ const D3DKMDT_MONITOR_SOURCE_MODE CONST *pMonitorSourceModeInfo
)
{ ... }
````


## -parameters

### -param hMonitorSourceModeSet [in]

[in] A handle to a monitor source mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function of the <a href="display.monitor_interface">Monitor interface</a>.

### -param pMonitorSourceModeInfo [in]

[in] A pointer to a <a href="display.d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure that describes the monitor source mode. The display miniport driver previously obtained this structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>.

## -returns
The <b>pfnAddMode</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The function failed because it could not allocate enough memory.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_SOURCE_MODE</b></dt>
</dl>The information supplied in <i>pMonitorSourceModeInfo</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_SOURCEMODESET</b></dt>
</dl>The handle supplied in <i>hMonitorSourceModeSet</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_FREQUENCY</b></dt>
</dl>The frequency information supplied in <i>pMonitorSourceModeInfo</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_ACTIVE_REGION</b></dt>
</dl>The active region supplied in <i>pMonitorSourceModeInfo</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_TOTAL_REGION</b></dt>
</dl>The total region supplied in <i>pMonitorSourceModeInfo</i> was invalid.
<dl>
<dt><b>STATUS_GRAPHICS_MODE_ALREADY_IN_MODE_SET</b></dt>
</dl>The mode set already contains a mode that is identical to the mode supplied in <i>pMonitorSourceModeInfo</i>.
<dl>
<dt><b>STATUS_GRAPHICS_MODE_ID_MUST_BE_UNIQUE</b></dt>
</dl>The identifier supplied in pMonitorSourceModeInfo-&gt;Id is already being used for another mode in the mode set.
<dl>
<dt><b>STATUS_GRAPHICS_RESOURCES_NOT_RELATED</b></dt>
</dl>The structure pointed to by <i>pMonitorSourceModeInfo</i> was not created for addition to the mode set specified by <i>hMonitorSourceModeSet</i>.

 

## -remarks
If <i>pMonitorSourceModeInfo</i>-&gt;<b>Preference</b> is equal to D3DKMDT_MP_PREFERRED, the newly added mode becomes the preferred mode of the mode set.

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

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorsourcemodeset_createnewmodeinfo.md">pfnCreateNewModeInfo</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_MONITORSOURCEMODESET_ADDMODE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
