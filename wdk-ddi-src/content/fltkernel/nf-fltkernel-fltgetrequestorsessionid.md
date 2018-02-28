---
UID: NF:fltkernel.FltGetRequestorSessionId
title: FltGetRequestorSessionId function
author: windows-driver-content
description: The FltGetRequestorSessionId routine returns the session ID of the process that originally requested the specified I/O operation.
old-location: ifsk\fltgetrequestorsessionid.htm
old-project: ifsk
ms.assetid: 6a0eb588-fe64-4f36-8648-8e006e16704e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltGetRequestorSessionId, FltGetRequestorSessionId routine [Installable File System Drivers], fltkernel/FltGetRequestorSessionId, ifsk.fltgetrequestorsessionid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 7 and later versions of the Windows operating system.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetRequestorSessionId
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetRequestorSessionId function
The <b>FltGetRequestorSessionId</b> routine returns the session ID of the process that originally requested the specified I/O operation.

## Syntax

````
NTSTATUS FltGetRequestorSessionId(
  _In_  PFLT_CALLBACK_DATA CallbackData,
  _Out_ PULONG             SessionId
);
````

## Parameters

`CallbackData`

A pointer to the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure specifying the I/O operation.

`SessionId`

A pointer to the session ID for the requesting operation.


## Return Value

The <b>FltGetRequestorSessionId</b> routine returns STATUS_SUCCESS on success or STATUS_UNSUCCESSFUL on failure.

## Remarks

If a process has no session ID, the SessionId parameter refers to -1 and the <b>FltGetRequestorSessionId</b> routine returns STATUS_SUCCESS.

If the <b>FltGetRequestorSessionId</b> routine returns STATUS_UNSUCCESSFUL, <i>SessionId</i> is not valid.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows 7 and later versions of the Windows operating system.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include FltKernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |