---
UID: NS.d3dumddi.D3DDDICB_EVICT
title: D3DDDICB_EVICT
author: windows-driver-content
description: D3DKMT_EVICT is used with pfnEvictCb to subtract one from the residency reference count.
old-location: display\d3dddicb_evict.htm
ms.assetid: 65743D54-3954-4C31-B3CB-032DE391A456
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_EVICT
req.alt-loc: d3dumddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
ms.keywords: D3DDDICB_EVICT, D3DDDICB_EVICT
req.iface: 
---

# D3DDDICB_EVICT structure



## -description
<p><b>D3DKMT_EVICT</b> is used with <a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a> to subtract one from the residency reference count.</p>
<p>Once this count reaches zero, it will remove the allocation from the device residency list.
  </p>


## -syntax

````
typedef struct D3DDDICB_EVICT {
  UINT                NumAllocations;
  const D3DKMT_HANDLE *AllocationList;
  D3DDDI_EVICT_FLAGS  Flags;
  UINT64              NumBytesToTrim;
} D3DDDICB_EVICT;
````


## -struct-fields
<dl>

### -field <b>NumAllocations</b>

<dd>
<p>[in] Number of allocation handles in the <b>AllocationList</b> array.</p>
</dd>

### -field <b>AllocationList</b>

<dd>
<p>[in] An array of <b>NumAllocations</b> allocation handles to mark for eviction. All allocations must be created on <b>hDevice</b>.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] Specifies eviction behavior as documented in <a href="https://msdn.microsoft.com/library/windows/hardware/dn906322">D3DDDI_EVICT_FLAGS</a>. </p>
</dd>

### -field <b>NumBytesToTrim</b>

<dd>
<p>[out] When non-zero, specifies how much the application should evict in order to meet its current memory budget.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/5E66A522-BC1C-4E7C-8732-87D40F99BBDA">pfnEvictCb</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn906322">D3DDDI_EVICT_FLAGS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_EVICT structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
