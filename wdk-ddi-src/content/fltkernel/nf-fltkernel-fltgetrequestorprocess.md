---
UID: NF:fltkernel.FltGetRequestorProcess
title: FltGetRequestorProcess function
author: windows-driver-content
description: The FltGetRequestorProcess routine returns a process pointer for the thread that requested a given I/O operation.
old-location: ifsk\fltgetrequestorprocess.htm
old-project: ifsk
ms.assetid: be734d14-64ee-47f0-8df9-4c4b8830448d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_9705ecf7-4e60-4b9a-b07e-4e24227aff1d.xml, FltGetRequestorProcess, FltGetRequestorProcess routine [Installable File System Drivers], fltkernel/FltGetRequestorProcess, ifsk.fltgetrequestorprocess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetRequestorProcess
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetRequestorProcess function
The <b>FltGetRequestorProcess</b> routine returns a process pointer for the thread that requested a given I/O operation.

## Syntax

````
PEPROCESS FltGetRequestorProcess(
  _In_ PFLT_CALLBACK_DATA CallbackData
);
````

## Parameters

`CallbackData`

Pointer to the callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) for the I/O operation.


## Return Value

<b>FltGetRequestorProcess</b> returns a process pointer for the thread that requested the I/O operation. If the operation is not associated with any thread, <b>FltGetRequestorProcess</b> returns <b>NULL</b>.

## Remarks

<b>FltGetRequestorProcess</b> returns a pointer to the process that the requesting thread is currently attached to. This process may or may not be the same process that created the thread.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltgetrequestorprocessid.md">FltGetRequestorProcessId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetRequestorProcess routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>