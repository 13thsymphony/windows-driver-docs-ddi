---
UID: NF:rxtimer.RxCancelTimerRequest
title: RxCancelTimerRequest function
author: windows-driver-content
description: RxCancelTimerRequest cancels a recurrent timer request. The request to be canceled is identified by the worker thread routine and associated context.
old-location: ifsk\rxcanceltimerrequest.htm
old-project: ifsk
ms.assetid: b5aeb972-3e52-4cdc-842b-7848bb2f8dc7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxCancelTimerRequest, RxCancelTimerRequest routine [Installable File System Drivers], ifsk.rxcanceltimerrequest, rxref_f9950992-18a5-4418-a18d-e105ecdc74ff.xml, rxtimer/RxCancelTimerRequest
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
req.lib: 
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
-	RxCancelTimerRequest
product:
- Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---


# RxCancelTimerRequest function
<b>RxCancelTimerRequest</b> cancels a recurrent timer request. The request to be canceled is identified by the worker thread routine and associated context.

## Syntax

```
NTSTATUS RxCancelTimerRequest(
  IN PRDBSS_DEVICE_OBJECT     pDeviceObject,
  IN PRX_WORKERTHREAD_ROUTINE Routine,
  IN PVOID                    pContext
);
```

## Parameters

`pDeviceObject`

A pointer to the device object that initialized the timer. This parameter was passed to the <b>RxPostRecurrentTimerRequest</b> routine when this recurrent timer was initialized.

`Routine`

A pointer to the worker thread routine to call when this timer expires. This parameter was passed to the <b>RxPostRecurrentTimerRequest</b> routine when this recurrent timer was initialized.

`pContext`

A pointer to the context parameter that was passed to the <b>RxPostRecurrentTimerRequest</b> routine when this timer was initialized.


## Return Value

<b>RxCancelTimerRequest</b> returns STATUS_SUCCESS on success.

## Remarks

A recurrent timer is initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554615">RxPostRecurrentTimerRequest</a>.

If the recurrent timer is not found, this routine will return STATUS_NOT_FOUND.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxtimer.h (include Rxtimer.h, Rxworkq.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554612">RxPostOneShotTimerRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554615">RxPostRecurrentTimerRequest</a>