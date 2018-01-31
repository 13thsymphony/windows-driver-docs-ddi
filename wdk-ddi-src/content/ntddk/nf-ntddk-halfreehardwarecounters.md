---
UID : NF:ntddk.HalFreeHardwareCounters
title : HalFreeHardwareCounters function
author : windows-driver-content
description : The HalFreeHardwareCounters routine frees a set of hardware performance counters that was acquired in a previous call to HalAllocateHardwareCounters routine.
old-location : kernel\halfreehardwarecounters.htm
old-project : kernel
ms.assetid : 646a073b-e0c5-4d41-b60c-3935c129fb39
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : HalFreeHardwareCounters routine [Kernel-Mode Driver Architecture], kernel.halfreehardwarecounters, ntddk/HalFreeHardwareCounters, k103_7516fb8d-7064-4f4a-bbef-a979809bf011.xml, HalFreeHardwareCounters
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hal.lib
req.dll : Hal.dll
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# HalFreeHardwareCounters function
The <b>HalFreeHardwareCounters</b> routine frees a set of hardware performance counters that was acquired in a previous call to <a href="..\ntddk\nf-ntddk-halallocatehardwarecounters.md">HalAllocateHardwareCounters</a> routine.

## Syntax

````
NTSTATUS HalFreeHardwareCounters(
  _In_ HANDLE CounterSetHandle
);
````

## Parameters

`CounterSetHandle`

A handle to the allocated counter resources. The caller acquired this handle in a previous call to <b>HalAllocateHardwareCounters</b>.


## Return Value

<b>HalFreeHardwareCounters</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>CounterSetHandle</i> is not a valid counter resources handle.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddk\nf-ntddk-halallocatehardwarecounters.md">HalAllocateHardwareCounters</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20HalFreeHardwareCounters routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>