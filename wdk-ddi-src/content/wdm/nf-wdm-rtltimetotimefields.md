---
UID : NF:wdm.RtlTimeToTimeFields
title : RtlTimeToTimeFields function
author : windows-driver-content
description : The RtlTimeToTimeFields routine converts system time into a TIME_FIELDS structure.
old-location : kernel\rtltimetotimefields.htm
old-project : kernel
ms.assetid : 128fe592-8dc1-46cf-8aa6-0f3de0896cc5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlTimeToTimeFields routine [Kernel-Mode Driver Architecture], wdm/RtlTimeToTimeFields, k109_574f7b2f-cbb5-447c-84d5-88179cbe4cb7.xml, RtlTimeToTimeFields, kernel.rtltimetotimefields
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
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
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql : Any level (See Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlTimeToTimeFields function
The RtlTimeToTimeFields routine converts system time into a <b>TIME_FIELDS</b> structure.

## Syntax

````
VOID RtlTimeToTimeFields(
  _In_  PLARGE_INTEGER Time,
  _Out_ PTIME_FIELDS   TimeFields
);
````

## Parameters

`Time`

Pointer to a buffer containing the absolute system time as a large integer, accurate to 100-nanosecond resolution.

`TimeFields`

Pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<b>TIME_FIELDS</b>), to contain the returned information.


## Return Value

None

## Remarks

Callers of <b>RtlTimeToTimeFields</b> can be running at any IRQL if both input buffers are resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level (See Remarks section) |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-exlocaltimetosystemtime.md">ExLocalTimeToSystemTime</a>

<a href="..\wdm\nf-wdm-rtltimefieldstotime.md">RtlTimeFieldsToTime</a>

<a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a>

<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlTimeToTimeFields routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>