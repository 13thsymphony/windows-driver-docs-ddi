---
UID: NS.D3DKMDDI._DXGKARG_GETROOTPAGETABLESIZE
title: _DXGKARG_GETROOTPAGETABLESIZE
author: windows-driver-content
description: DXGKARG_GETROOTPAGETABLESIZE is used with DxgkDdiGetRootPageTableSize.
old-location: display\dxgkarg_getrootpagetablesize.htm
old-project: display
ms.assetid: 31CB33F9-87E8-419D-AF35-E7F731661DD5
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKARG_GETROOTPAGETABLESIZE, DXGKARG_GETROOTPAGETABLESIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_GETROOTPAGETABLESIZE
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

# _DXGKARG_GETROOTPAGETABLESIZE structure



## -description
<b>DXGKARG_GETROOTPAGETABLESIZE</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getrootpagetablesize.md">DxgkDdiGetRootPageTableSize</a>.



## -syntax

````
typedef struct _DXGKARG_GETROOTPAGETABLESIZE {
  UINT NumberOfPte;
  UINT PhysicalAdapterIndex;
} DXGKARG_GETROOTPAGETABLESIZE;
````


## -struct-fields

### -field NumberOfPte

[in] A pointer to the number of page table entries which are required to be in the root page table.

[out] The actual number of page table entries in the page table with the returned size.


### -field PhysicalAdapterIndex

Physical adapter index (zero for non-linked display adapter configurations).


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
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getrootpagetablesize.md">DxgkDdiGetRootPageTableSize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_GETROOTPAGETABLESIZE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

