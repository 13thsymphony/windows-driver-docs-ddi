---
UID: NS.D3DKMTHK._D3DKMT_QUERYALLOCATIONRESIDENCY
title: _D3DKMT_QUERYALLOCATIONRESIDENCY
author: windows-driver-content
description: The D3DKMT_QUERYALLOCATIONRESIDENCY structure describes information for retrieving the residency status from a resource or list of allocations.
old-location: display\d3dkmt_queryallocationresidency.htm
old-project: display
ms.assetid: 53dd0306-4dcc-47a0-aa98-67d289c93b9b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_QUERYALLOCATIONRESIDENCY, D3DKMT_QUERYALLOCATIONRESIDENCY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_QUERYALLOCATIONRESIDENCY
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_QUERYALLOCATIONRESIDENCY structure



## -description
The D3DKMT_QUERYALLOCATIONRESIDENCY structure describes information for retrieving the residency status from a resource or list of allocations. 



## -syntax

````
typedef struct _D3DKMT_QUERYALLOCATIONRESIDENCY {
  D3DKMT_HANDLE                    hDevice;
  D3DKMT_HANDLE                    hResource;
  const D3DKMT_HANDLE              *phAllocationList;
  UINT                             AllocationCount;
  D3DKMT_ALLOCATIONRESIDENCYSTATUS *pResidencyStatus;
} D3DKMT_QUERYALLOCATIONRESIDENCY;
````


## -struct-fields

### -field hDevice

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the device that the resource or list of allocations are associated with.


### -field hResource

[in] A handle to a resource whose residency is queried. If the OpenGL ICD uses the array that <b>phAllocationList</b> specifies to query for residency, it sets <b>hResource</b> to <b>NULL</b>. If the OpenGL ICD sets <b>hResource</b> to a non-<b>NULL</b> value, it must set the <b>AllocationCount</b> member to zero and <b>phAllocationList</b> to <b>NULL</b>. 

If <b>hResource</b> is non-<b>NULL</b>, all of the allocations that belong to the resource are queried, and the result is returned in the first element of the array that <b>pResidencyStatus</b> points to. 

If any allocation that belongs to the resource is not resident, the entire resource is considered not resident.

To retrieve detailed residency information about each allocation that belongs to a resource, the allocation must be queried.


### -field phAllocationList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The OpenGL ICD uses these handles to query for residency status. 

If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>phAllocationList</b> to <b>NULL</b>. 


### -field AllocationCount

[in] The number of allocations in the array that <b>phAllocationList</b> specifies. If the OpenGL ICD sets the handle in the <b>hResource</b> member to a non-<b>NULL</b> value, it must set <b>AllocationCount</b> to zero.


### -field pResidencyStatus

[out] A pointer to an array of D3DKMT_ALLOCATIONRESIDENCYSTATUS enumerators. If the <b>hResource</b> member is non-<b>NULL</b>, the array contains a single element and receives one of the enumerators that are listed in the following table to indicate the residency status of the resource. If <b>hResource</b> is <b>NULL</b>, the number of elements in the array is specified by the <b>AllocationCount</b> member, and each element receives one of the following enumerators to indicate the residency status of the corresponding allocation in the <b>phAllocationList</b> array.

<table>
<tr>
<th>Enumerator</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DKMT_ALLOCATIONRESIDENCYSTATUS_RESIDENTINGPUMEMORY (1)

</td>
<td>
The resource or allocation resides in GPU memory.

</td>
</tr>
<tr>
<td>
D3DKMT_ALLOCATIONRESIDENCYSTATUS_RESIDENTINSHAREDMEMORY (2)

</td>
<td>
The resource or allocation resides in shared memory.

</td>
</tr>
<tr>
<td>
D3DKMT_ALLOCATIONRESIDENCYSTATUS_NOTRESIDENT (3)

</td>
<td>
The resource or allocation is nonresident.

</td>
</tr>
</table>
 


## -remarks


## -requirements
<table>
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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmtqueryallocationresidency">D3DKMTQueryAllocationResidency</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_QUERYALLOCATIONRESIDENCY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

