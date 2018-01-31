---
UID : NF:ks.KsDecrementCountedWorker
title : KsDecrementCountedWorker function
author : windows-driver-content
description : Decrements the current worker count of a worker previous created by KsRegisterCountedWorker. This should be called after each task within a worker has been completed.
old-location : stream\ksdecrementcountedworker.htm
old-project : stream
ms.assetid : 2b38e4df-e5b6-480b-bd4e-62e059e26411
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksdecrementcountedworker, ks/KsDecrementCountedWorker, KsDecrementCountedWorker function [Streaming Media Devices], ksfunc_7ddba520-3deb-4160-87e1-a12d2210b5da.xml, KsDecrementCountedWorker
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
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
req.lib : Ks.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsDecrementCountedWorker function
Decrements the current worker count of a worker previous created by <a href="..\ks\nf-ks-ksregistercountedworker.md">KsRegisterCountedWorker</a>. This should be called after each task within a worker has been completed.

## Syntax

````
ULONG KsDecrementCountedWorker(
  _In_ PKSWORKER Worker
);
````

## Parameters

`Worker`

Contains the previously allocated worker.


## Return Value

Returns the current counter. A count of zero implies that the task list has been completed.

## Remarks

<b>KsDecrementCountedWorker</b> should be called after each task within a worker has been completed. A corresponding call to <a href="..\ks\nf-ks-ksincrementcountedworker.md">KsIncrementCountedWorker</a> would have previously incremented the count. <b>KsDecrementCountedWorker</b> may be called at DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\nf-ks-ksregistercountedworker.md">KsRegisterCountedWorker</a>

<a href="..\ks\nf-ks-ksincrementcountedworker.md">KsIncrementCountedWorker</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDecrementCountedWorker function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>