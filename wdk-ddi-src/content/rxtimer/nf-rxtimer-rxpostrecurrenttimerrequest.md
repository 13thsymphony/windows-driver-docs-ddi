---
UID: NF:rxtimer.RxPostRecurrentTimerRequest
title: RxPostRecurrentTimerRequest function
author: windows-driver-content
description: RxPostRecurrentTimerRequest initializes a recurrent timer request. The passed in pointer to a worker thread routine is called at regular intervals when the recurrent timer fires based on the input parameters to this routine.
old-location: ifsk\rxpostrecurrenttimerrequest.htm
old-project: ifsk
ms.assetid: a44fb478-4f78-415e-b557-bf383199578c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxPostRecurrentTimerRequest, RxPostRecurrentTimerRequest routine [Installable File System Drivers], ifsk.rxpostrecurrenttimerrequest, rxref_64318843-28af-4351-9273-06061b94578f.xml, rxtimer/RxPostRecurrentTimerRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxtimer.h
req.include-header: Rxtimer.h, Rxworkq.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxtimer.h
api_name:
-	RxPostRecurrentTimerRequest
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---


# RxPostRecurrentTimerRequest function
<b>RxPostRecurrentTimerRequest</b> initializes a recurrent timer request. The passed in pointer to a worker thread routine is called at regular intervals when the recurrent timer fires based on the input parameters to this routine.

## Syntax

````
NTSTATUS RxPostRecurrentTimerRequest(
  _In_ PRDBSS_DEVICE_OBJECT     pDeviceObject,
  _In_ PRX_WORKERTHREAD_ROUTINE Routine,
  _In_ PVOID                    pContext,
  _In_ LARGE_INTEGER            TimeInterval
);
````

## Parameters

`pDeviceObject`

A pointer to the device object to be associated with this timer.

`Routine`

A pointer to the worker thread routine to call when this timer expires.

`pContext`

A pointer to the context parameter to be associated with this timer.

`TimeInterval`

The time interval, in 100-nanosecond ticks.


## Return Value

<b>RxPostRecurrentTimerRequest</b> returns STATUS_SUCCESS on success or one of the following error codes: 

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
The allocation of non-paged pool memory required by this routine failed. 

</td>
</tr>
</table>

## Remarks

A recurrent timer can be canceled by calling <b>RxCancelTimerRequest</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxtimer.h (include Rxtimer.h, Rxworkq.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\rxtimer\nf-rxtimer-rxpostoneshottimerrequest.md">RxPostOneShotTimerRequest</a>



<a href="..\rxtimer\nf-rxtimer-rxcanceltimerrequest.md">RxCancelTimerRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPostRecurrentTimerRequest routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>