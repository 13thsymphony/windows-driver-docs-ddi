---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO
title: DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO
author: windows-driver-content
description: The pfnAcquireNextDescriptorInfo function returns the next descriptor in a monitor descriptor set, given the current descriptor.
old-location: display\dxgk_monitordescriptorset_interface_pfnacquirenextdescriptorinfo.htm
old-project: display
ms.assetid: 34d048df-d4a1-4ef5-b917-791f35de9e3a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_monitordescriptorset_interface_pfnacquirenextdescriptorinfo, pfnAcquireNextDescriptorInfo callback function [Display Devices], pfnAcquireNextDescriptorInfo, DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO, DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO, d3dkmddi/pfnAcquireNextDescriptorInfo, VidPnFunctions_ae273fb1-032c-4d22-86ef-849a4650c82e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	pfnAcquireNextDescriptorInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO callback function
The <b>pfnAcquireNextDescriptorInfo</b> function returns the next descriptor in a monitor descriptor set, given the current descriptor.

## Syntax

```
DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO DxgkddiMonitordescriptorsetAcquirenextdescriptorinfo;

NTSTATUS DxgkddiMonitordescriptorsetAcquirenextdescriptorinfo(
  IN_CONST_D3DKMDT_HMONITORDESCRIPTORSET hMonitorDescriptorSet,
  IN_CONST_PD3DKMDT_MONITOR_DESCRIPTOR_CONST pMonitorDescriptorInfo,
  DEREF_OUT_CONST_PPD3DKMDT_MONITOR_DESCRIPTOR ppNextMonitorDescriptorInfo
)
{...}
```

## Parameters

`hMonitorDescriptorSet`

[in] A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md">pfnGetMonitorDescriptorSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.

`pMonitorDescriptorInfo`

[in] A pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_descriptor.md">D3DKMDT_MONITOR_DESCRIPTOR</a> structure that is the current descriptor. The display miniport driver previously obtained this pointer by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo.md">pfnAcquireFirstDescriptorInfo</a> or <b>pfnAcquireNextDescriptorInfo</b>.

`ppNextMonitorDescriptorInfo`

[out] A pointer to a variable that receives a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_monitor_descriptor.md">D3DKMDT_MONITOR_DESCRIPTOR</a> structure. The structure is the next descriptor in the set.


## Return Value

The <b>pfnAcquireNextDescriptorInfo</b> function returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function successfully returned the next descriptor in the set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NO_MORE_ELEMENTS_IN_DATASET</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded, but there were no more descriptors in the set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_MONITOR_DESCRIPTOR</b></dt>
</dl>
</td>
<td width="60%">
The descriptor supplied in <i>pMonitorDescriptorInfo</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hMonitorDescriptorSet</i> was invalid.

</td>
</tr>
</table>

## Remarks

When you have finished using the D3DKMDT_MONITOR_DESCRIPTOR structure, you must release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo.md">pfnReleaseDescriptorInfo</a>.

You can obtain all the descriptors in a monitor descriptor set by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo.md">pfnAcquireFirstDescriptorInfo</a> and then making a sequence of calls to <b>pfnAcquireNextDescriptorInfo</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |