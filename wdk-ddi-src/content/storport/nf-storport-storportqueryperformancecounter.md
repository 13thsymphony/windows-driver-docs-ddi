---
UID: NF:storport.StorPortQueryPerformanceCounter
title: StorPortQueryPerformanceCounter function
author: windows-driver-content
description: The current system performance counter value is queried is returned by the StorPortQueryPerformanceCounter routine.
old-location: storage\storportqueryperformancecounter.htm
old-project: storage
ms.assetid: 6502E3AE-5841-41C9-BEB7-B00620DBF02D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortQueryPerformanceCounter, StorPortQueryPerformanceCounter routine [Storage Devices], storage.storportqueryperformancecounter, storport/StorPortQueryPerformanceCounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Storport.h
api_name:
-	StorPortQueryPerformanceCounter
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortQueryPerformanceCounter function
The current system performance counter value is queried is returned by the <b>StorPortQueryPerformanceCounter</b> routine.. The performance frequency is also returned as an optional parameter.

## Syntax

````
ULONG StorPortQueryPerformanceCounter(
  _In_      PVOID          HwDeviceExtension,
  _Out_opt_ PLARGE_INTEGER PerformanceFrequency,
  _Out_     PLARGE_INTEGER PerformanceCounter
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`PerformanceFrequency`

A pointer to a large integer to receive the current system performance frequency value. This parameter is optional and can be NULL.

`PerformanceCounter`

A pointer to a large integer to receive the current system performance counter value.


## Return Value

<b>StorPortQueryPerformanceCounter</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The performance counter value is returned in the large integer pointed to by <i>PerformanceCounter</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>PerformanceCounter</i> parameter is <b>NULL</b>.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **IRQL** | Any |

## See Also

<a href="..\storport\nf-storport-storportquerysystemtime.md">StorPortQuerySystemTime</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortQueryPerformanceCounter routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>