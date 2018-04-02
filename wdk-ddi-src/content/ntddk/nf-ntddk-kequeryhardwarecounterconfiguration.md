---
UID: NF:ntddk.KeQueryHardwareCounterConfiguration
title: KeQueryHardwareCounterConfiguration function
author: windows-driver-content
description: The KeQueryHardwareCounterConfiguration routine queries the operating system for the list of hardware counters to use for thread profiling.
old-location: kernel\kequeryhardwarecounterconfiguration.htm
old-project: kernel
ms.assetid: 5ac33177-38fc-4027-95c9-c2cf9ccdaa52
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeQueryHardwareCounterConfiguration, KeQueryHardwareCounterConfiguration routine [Kernel-Mode Driver Architecture], k105_442c5acf-84a3-4078-b401-ca8cb8069c6e.xml, kernel.kequeryhardwarecounterconfiguration, ntddk/KeQueryHardwareCounterConfiguration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryHardwareCounterConfiguration
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# KeQueryHardwareCounterConfiguration function
The <b>KeQueryHardwareCounterConfiguration</b> routine queries the operating system for the list of hardware counters to use for thread profiling.

## Syntax

```
NTKERNELAPI NTSTATUS KeQueryHardwareCounterConfiguration(
  PHARDWARE_COUNTER CounterArray,
  ULONG             MaximumCount,
  PULONG            Count
);
```

## Parameters

`CounterArray`

A pointer to a caller-allocated buffer into which the routine writes an array of elements of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff546980">HARDWARE_COUNTER</a>. Each array element is a structure that contains information about a hardware counter. The array contains one element for each hardware counter that is assigned to thread profiling. If the routine fails, it writes nothing to this buffer.

`MaximumCount`

Specifies the maximum number of elements that the routine can write to the buffer that is pointed to by the <i>CounterArray</i> parameter. The size of the caller-allocated buffer must be at least <i>MaximumCount</i> * <b>sizeof</b>(<b>HARDWARE_COUNTER</b>) bytes.

`Count`

A pointer to a location into which the routine writes the number of array elements that it has written to the buffer that is pointed to by the <i>CounterArray</i> parameter. If the buffer length that is specified by <i>MaximumCount</i> is not large enough to contain the entire array, the routine writes the required length to *<i>Count</i> and returns STATUS_BUFFER_TOO_SMALL.


## Return Value

<b>KeQueryHardwareCounterConfiguration</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>MaximumCount</i> parameter specifies a buffer length that is not large enough to contain the counter configuration information. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This routine is not implemented for the processor architecture that the caller is running on. 

</td>
</tr>
</table>

## Remarks

In Windows 7, this routine is implemented only for the x86-based, x64-based, and Itanium-based architectures. If the caller is running on a processor architecture that is not supported, the routine returns STATUS_NOT_IMPLEMENTED. 

To set the hardware counter configuration to use for thread profiling, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553257">KeSetHardwareCounterConfiguration</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546980">HARDWARE_COUNTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553257">KeSetHardwareCounterConfiguration</a>