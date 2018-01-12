---
UID: NC:d3dkmddi.DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO
title: DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO
author: windows-driver-content
description: The pfnReleaseFrequencyRangeInfo function releases a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_monitorfrequencyrangeset_interface_pfnreleasefrequencyrangeinfo.htm
old-project: display
ms.assetid: 54e3d08b-5f0d-4d98-9b93-e2aec96d3362
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
req.alt-api: pfnReleaseFrequencyRangeInfo
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

# DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO callback



## -description
The <b>pfnReleaseFrequencyRangeInfo</b> function releases a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_frequency_range.md">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure that the VidPN manager previously provided to the display miniport driver.



## -prototype

````
DXGKDDI_MONITORFREQUENCYRANGESET_RELEASEFREQUENCYRANGEINFO pfnReleaseFrequencyRangeInfo;

NTSTATUS APIENTRY pfnReleaseFrequencyRangeInfo(
  _In_ const D3DKMDT_HMONITORFREQUENCYRANGESET     hMonitorFrequencyRangeSet,
  _In_ const D3DKMDT_MONITOR_FREQUENCY_RANGE CONST *pMonitorFrequencyRangeInfo
)
{ ... }
````


## -parameters

### -param hMonitorFrequencyRangeSet [in]

[in] A handle to a monitor frequency range set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md">pfnGetMonitorFrequencyRangeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pMonitorFrequencyRangeInfo [in]

[in] A pointer to the D3DKMDT_MONITOR_FREQUENCY_RANGE structure that is to be released.


## -returns
The <b>pfnAcquireNextFrequencyRangeInfo</b> function returns one of the following values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_INVALID_MONITOR_FREQUENCY_RANGE</b></dt>
</dl>The frequency range descriptor supplied in <i>pMonitorFrequencyRangeInfo</i> was invalid.
<dl>
<dt><b>STATUS_INVALID_MONITOR_FREQUENCYRANGESET</b></dt>
</dl>The handle supplied in <i>hMonitorFrequencyRangeSet</i> was invalid.

 


## -remarks
When you have finished using a D3DKMDT_MONITOR_FREQUENCY_RANGE structure that you obtained by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirefirstfrequencyrangeinfo.md">pfnAcquireFirstFrequencyRangeInfo</a> or <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitorfrequencyrangeset_acquirenextfrequencyrangeinfo.md">pfnAcquireNextFrequencyRangeInfo</a>, you must release it by calling <b>pfnReleaseFrequencyRangeInfo</b>.


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