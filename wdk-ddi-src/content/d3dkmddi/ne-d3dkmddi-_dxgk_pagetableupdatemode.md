---
UID: NE.d3dkmddi._DXGK_PAGETABLEUPDATEMODE
title: _DXGK_PAGETABLEUPDATEMODE
author: windows-driver-content
description: DXGK_PAGETABLEUPDATEMODE is used as part of a DxgkDdiBuildPagingBuffer operation to indicate which member of the related DXGK_PAGETABLEUPDATEADDRESS structure contains the address of the page table to update.
old-location: display\dxgk_pagetableupdatemode.htm
old-project: display
ms.assetid: E7C823B1-457E-4B86-B44B-DC5BD48CF98E
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PAGETABLEUPDATEMODE, DXGK_PAGETABLEUPDATEMODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_PAGETABLEUPDATEMODE
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

# _DXGK_PAGETABLEUPDATEMODE enumeration



## -description
<b>DXGK_PAGETABLEUPDATEMODE</b> is used as part of a <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> operation to indicate which member of the related <a href="display.dxgk_pagetableupdateaddress">DXGK_PAGETABLEUPDATEADDRESS</a> structure contains the address of the page table to update. 



## -syntax

````
typedef enum _DXGK_PAGETABLEUPDATEMODE { 
  DXGK_PAGETABLEUPDATE_CPU_VIRTUAL,
  DXGK_PAGETABLEUPDATE_GPU_VIRTUAL,
  DXGK_PAGETABLEUPDATE_GPU_PHYSICAL
} DXGK_PAGETABLEUPDATEMODE;
````


## -enum-fields

### -field DXGK_PAGETABLEUPDATE_CPU_VIRTUAL

Indicates that the address of the page table to update is in the <b>CpuVirtual</b> member of the <a href="display.dxgk_pagetableupdateaddress">DXGK_PAGETABLEUPDATEADDRESS</a> structure.


### -field DXGK_PAGETABLEUPDATE_GPU_VIRTUAL

Indicates that the address of the page table to update is in the <b>GpuVirtual</b> member of the <a href="display.dxgk_pagetableupdateaddress">DXGK_PAGETABLEUPDATEADDRESS</a> structure.


### -field DXGK_PAGETABLEUPDATE_GPU_PHYSICAL

Indicates that the address of the page table to update is in the <b>GpuPhysical</b> member of the <a href="display.dxgk_pagetableupdateaddress">DXGK_PAGETABLEUPDATEADDRESS</a> structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>
</dt>
<dt>
<a href="display.dxgk_pagetableupdateaddress">DXGK_PAGETABLEUPDATEADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_PAGETABLEUPDATEMODE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

