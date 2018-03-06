---
UID: NF:rxworkq.RxSpinDownMRxDispatcher
title: RxSpinDownMRxDispatcher function
author: windows-driver-content
description: RxSpinDownMRxDispatcher tears down the dispatcher context for a network mini-redirector.
old-location: ifsk\rxspindownmrxdispatcher.htm
old-project: ifsk
ms.assetid: 0ec10c43-df57-4661-9106-8edc6b76f5d7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxSpinDownMRxDispatcher, RxSpinDownMRxDispatcher function [Installable File System Drivers], ifsk.rxspindownmrxdispatcher, rxref_aa43a136-8df7-45f1-bf52-48792c094f31.xml, rxworkq/RxSpinDownMRxDispatcher
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxworkq.h
req.include-header: Rxworkq.h, Rxstruc.h
req.target-type: Desktop
req.target-min-winverclnt: The RxSpinDownMRxDispatcher routine is only available on Windows XP and later.
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
-	rxworkq.h
api_name:
-	RxSpinDownMRxDispatcher
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---


# RxSpinDownMRxDispatcher function
<b>RxSpinDownMRxDispatcher</b> tears down the dispatcher context for a network mini-redirector.

## Syntax

````
NTSTATUS RxSpinDownMRxDispatcher(
  _Inout_ PRDBSS_DEVICE_OBJECT pMRxDeviceObject
);
````

## Parameters

`pMRxDeviceObject`

A pointer to the device object of the corresponding network mini-redirector driver.


## Return Value

<b>RxSpinDownMRxDispatcher</b> returns STATUS_SUCCESS on success. On checked builds, this routine causes the system to ASSERT on failure.

## Remarks

The <b>RxSpinDownMRxDispatcher</b> routine will set a tear down request into the driver device object of the network mini-redirector driver (the <b>DispatcherContext.pTearDownEvent</b> member of the device object is set to <b>&amp;TearDownEvent</b>) and wait for the driver to tear down any outstanding worker threads. 

The <b>RxSpinDownMRxDispatcher</b> routine is also called internally by the <b>RxStopMiniRdr</b> and <b>RxpUnregisterMinirdr</b> routines.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The RxSpinDownMRxDispatcher routine is only available on Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | rxworkq.h (include Rxworkq.h, Rxstruc.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\rxworkq\nf-rxworkq-rxdispatchtoworkerthread.md">RxDispatchToWorkerThread</a>



<a href="..\rxworkq\nf-rxworkq-rxposttoworkerthread.md">RxPostToWorkerThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxSpinDownMRxDispatcher function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>