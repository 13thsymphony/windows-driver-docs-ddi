---
UID: NS.D3DKMDDI._DXGKARG_SETROOTPAGETABLE
title: _DXGKARG_SETROOTPAGETABLE
author: windows-driver-content
description: DXGKARG_SETROOTPAGETABLE is used by the DxgkDdiSetRootPageTabledevice driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.
old-location: display\dxgkarg_setrootpagetable.htm
old-project: display
ms.assetid: D3863924-29EE-4886-B8DC-F9020A7C85A4
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGKARG_SETROOTPAGETABLE, DXGKARG_SETROOTPAGETABLE
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
req.alt-api: DXGKARG_SETROOTPAGETABLE
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

# _DXGKARG_SETROOTPAGETABLE structure



## -description
<b>DXGKARG_SETROOTPAGETABLE</b> is used by the <a href="display.dxgkddisetrootpagetable">DxgkDdiSetRootPageTable</a>device driver interface (DDI) to notify a context when its associated root page table is resized or moved in memory.


## -syntax

````
typedef struct _DXGKARG_SETROOTPAGETABLE {
  HANDLE                  hContext;
  D3DGPU_PHYSICAL_ADDRESS Address;
  UINT                    NumEntries;
} DXGKARG_SETROOTPAGETABLE;
````


## -struct-fields

### -field hContext

A context handle returned by <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>.

### -field Address

The GPU physical address of the root page table.

### -field NumEntries

 The root page table size in entries. GPU should generate invalid fault when a virtual address has a top level page table entry index, which is greater or equal this value.

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
<a href="display.dxgkddisetrootpagetable">DxgkDdiSetRootPageTable</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SETROOTPAGETABLE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
