---
UID: NF:ntddk.HalAllocateHardwareCounters
title: HalAllocateHardwareCounters function
author: windows-driver-content
description: The HalAllocateHardwareCounters routine allocates a set of hardware performance counters.
old-location: kernel\halallocatehardwarecounters.htm
old-project: kernel
ms.assetid: 8a689889-b445-4fda-ae11-090d0d5870b8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/HalAllocateHardwareCounters, HalAllocateHardwareCounters routine [Kernel-Mode Driver Architecture], HalAllocateHardwareCounters, kernel.halallocatehardwarecounters, k103_06a6696a-0b51-414e-96ea-6c7d3b70acb5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hal.dll
apiname:
-	HalAllocateHardwareCounters
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# HalAllocateHardwareCounters function
The <b>HalAllocateHardwareCounters</b> routine allocates a set of hardware performance counters.

## Syntax

````
NTSTATUS HalAllocateHardwareCounters(
  _In_  PGROUP_AFFINITY                 GroupAffinity,
  _In_  ULONG                           GroupCount,
  _In_  PPHYSICAL_COUNTER_RESOURCE_LIST ResourceList,
  _Out_ PHANDLE                         CounterSetHandle
);
````

## Parameters

`GroupAffinty`

TBD

`GroupCount`

Reserved for future use. Set this parameter to zero.

`ResourceList`

Reserved for future use. Set this parameter to <b>NULL</b>.

`CounterSetHandle`

A pointer to a location into which the routine writes a handle to the allocated counter resources. To release these resources later, the caller must pass this handle to the <a href="..\ntddk\nf-ntddk-halfreehardwarecounters.md">HalFreeHardwareCounters</a> routine. If the requested counter resources are unavailable, <b>HalAllocateHardwareCounters</b> sets *<i>CounterSetHandle</i> = <b>NULL</b> and returns STATUS_INSUFFICIENT_RESOURCES.


## Return Value

<b>HalAllocateHardwareCounters</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The requested counter resources are currently unavailable.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller specified an invalid parameter value.

</td>
</tr>
</table>

## Remarks

Most processors have performance monitor units (PMUs) that contain a number of hardware counters. Software tools use these counters to monitor various aspects of system performance. Typically, such a tool consists of a custom kernel-mode driver to program the counters and a user-mode application that communicates with the driver.

If more than one such tool is installed on a computer, the associated drivers must avoid trying to use the same hardware counters simultaneously. To avoid such resource conflicts, all drivers that use counter resources should use the <b>HalAllocateHardwareCounters</b> and <b>HalFreeHardwareCounters</b> routines to coordinate their sharing of these resources.

A counter resource is a single hardware counter, a block of contiguous counters, or a counter overflow interrupt in a PMU.

Before configuring the counters, a driver can call the <b>HalAllocateHardwareCounters</b> routine to acquire exclusive access to a set of counter resources. After the driver no longer needs these resources, it must free the resources by calling the <b>HalFreeHardwareCounters</b> routine.

In Windows 8 and Windows 7, a successful call to <b>HalAllocateHardwareCounters</b> grants the caller exclusive access to all counter resources in the performance monitor unit of a single-processor system. In a multiprocessor system, a successful call grants the caller exclusive access to all counter resources in all processors in the system. Future versions of this routine might provide more fine-grained allocation of counter resources.

Virtualization software typically does not virtualize hardware performance counters. Thus, these counters might not be available in a virtual machine, regardless of whether <b>HalAllocateHardwareCounters</b> returns a status code of STATUS_SUCCESS. For example, hardware performance counters are not available in a Hyper-V virtual machine, but <b>HalAllocateHardwareCounters</b> might still return STATUS_SUCCESS.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | Hal.lib |
| **DLL** | Hal.dll |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\miniport\ns-miniport-_group_affinity.md">GROUP_AFFINITY</a>



<a href="..\ntddk\ns-ntddk-_physical_counter_resource_list.md">PHYSICAL_COUNTER_RESOURCE_LIST</a>



<a href="..\ntddk\nf-ntddk-halfreehardwarecounters.md">HalFreeHardwareCounters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HalAllocateHardwareCounters routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>