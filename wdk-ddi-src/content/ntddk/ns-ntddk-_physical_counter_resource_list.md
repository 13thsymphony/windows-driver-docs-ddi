---
UID: NS.NTDDK._PHYSICAL_COUNTER_RESOURCE_LIST
title: _PHYSICAL_COUNTER_RESOURCE_LIST
author: windows-driver-content
description: The PHYSICAL_COUNTER_RESOURCE_LIST structure describes an array of PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR structures.
old-location: kernel\physical_counter_resource_list.htm
old-project: kernel
ms.assetid: a8b22839-6a5d-48e2-a0e5-dae811d729ef
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PHYSICAL_COUNTER_RESOURCE_LIST, *PPHYSICAL_COUNTER_RESOURCE_LIST, PHYSICAL_COUNTER_RESOURCE_LIST, PPHYSICAL_COUNTER_RESOURCE_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PHYSICAL_COUNTER_RESOURCE_LIST
req.alt-loc: ntddk.h
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

# _PHYSICAL_COUNTER_RESOURCE_LIST structure



## -description
The <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> structure describes an array of <a href="kernel.physical_counter_resource_descriptor">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a> structures.



## -syntax

````
typedef struct _PHYSICAL_COUNTER_RESOURCE_LIST {
  ULONG                                Count;
  PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR Descriptors[ANYSIZE_ARRAY];
} PHYSICAL_COUNTER_RESOURCE_LIST, *PPHYSICAL_COUNTER_RESOURCE_LIST;
````


## -struct-fields

### -field Count

The number of elements in the <b>Descriptors</b> array. 


### -field Descriptors

The first element in an array of <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> structures. If the array contains more than one element, the remaining elements immediately follow the first element. 


## -remarks
This structure describes a set of counter resources. Most processors have performance monitor units (PMUs) that contain a number of hardware counters to measure various aspects of system performance. A counter resource is a single hardware counter, a block of contiguous counters, or a counter overflow interrupt in a PMU.

The buffer allocated to contain a <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> structure must be large enough to contain the structure plus any <b>PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</b> array elements that follow the structure.

The <a href="kernel.halallocatehardwarecounters">HalAllocateHardwareCounters</a> routine's <i>ResourceList</i> parameter is a pointer to a <b>PHYSICAL_COUNTER_RESOURCE_LIST</b> structure. In Windows 7, this parameter is unused and must be set to <b>NULL</b>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.halallocatehardwarecounters">HalAllocateHardwareCounters</a>
</dt>
<dt>
<a href="kernel.physical_counter_resource_descriptor">PHYSICAL_COUNTER_RESOURCE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PHYSICAL_COUNTER_RESOURCE_LIST structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

