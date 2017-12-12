---
UID: NS.D3DUKMDT.D3DDDI_MAKERESIDENT
title: D3DDDI_MAKERESIDENT
author: windows-driver-content
description: D3DDDI_MAKERESIDENT is used with MakeResident (pfnMakeResidentCb or D3DKMTMakeResident) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dddi_makeresident.htm
old-project: display
ms.assetid: 16F04DFD-3AF6-48E0-9BCF-9FE0FC397F91
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DDDI_MAKERESIDENT, D3DDDI_MAKERESIDENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MAKERESIDENT
req.alt-loc: d3dukmdt.h
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
---

# D3DDDI_MAKERESIDENT structure



## -description
<b>D3DDDI_MAKERESIDENT</b> is used with <b>MakeResident</b> (<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a> or <a href="display.d3dkmtmakeresident">D3DKMTMakeResident</a>) to instruct the OS to add a resource to the device residency list and increment the residency reference count on this allocation.



## -syntax

````
typedef struct D3DDDI_MAKERESIDENT {
  D3DKMT_HANDLE             hPagingQueue;
  UINT                      NumAllocations;
  const D3DKMT_HANDLE       *AllocationList;
  const UINT                *PriorityList;
  D3DDDI_MAKERESIDENT_FLAGS Flags;
  UINT64                    PagingFenceValue;
  UINT64                    NumBytesToTrim;
} D3DDDI_MAKERESIDENT;
````


## -struct-fields

### -field hPagingQueue

[in] Paging queue on the device that created the input allocations. This queue will be used for residency operations.


### -field NumAllocations

[in/out] On input, the number of allocation handles in the <b>AllocationList</b> array and allocation priority values in the <b>PriorityList</b> array. On output,
                                                    the number of allocations successfully made resident.


### -field AllocationList

[in] An array of <b>NumAllocations</b> allocation handles to make resident. All allocations must be created on the device <b>hPagingQueue</b> is created for.


### -field PriorityList

[in] An array of <b>NumAllocations</b> specifying residency priority for each of the input allocations. This value is currently ignored and may be set to <b>NULL</b>.


### -field Flags

[in] Specifies memory residency behavior as documented in <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_makeresident_flags.md">D3DDDI_MAKERESIDENT_FLAGS</a>.


### -field PagingFenceValue

[out] When <b>MakeResident</b> returns <b>E_PENDING</b>, this member indicates the paging queue fence value to wait on. 


### -field NumBytesToTrim

[out] When <b>MakeResident</b> returns <b>E_OUTOFMEMORY</b>, this member indicates the number of bytes over budget the application would be if the allocation(s) were made resident. 


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
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_makeresidentcb.md">pfnMakeResidentCb</a>
</dt>
<dt>
<a href="display.d3dkmtmakeresident">D3DKMTMakeResident</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_makeresident_flags.md">D3DDDI_MAKERESIDENT_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MAKERESIDENT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

