---
UID: NF:fltkernel.FltPropagateActivityIdToThread
title: FltPropagateActivityIdToThread function
author: windows-driver-content
description: The FltPropagateActivityIdToThread routine associates the activity ID from the IRP in the minifilter's callback data with the current thread.
old-location: ifsk\fltpropagateactivityidtothread.htm
old-project: ifsk
ms.assetid: 7453EEB1-F974-4AEB-93C4-A75A79E1FE19
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltPropagateActivityIdToThread, FltPropagateActivityIdToThread routine [Installable File System Drivers], fltkernel/FltPropagateActivityIdToThread, ifsk.fltpropagateactivityidtothread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
-	FltPropagateActivityIdToThread
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltPropagateActivityIdToThread function
The <b>FltPropagateActivityIdToThread</b> routine associates the activity ID from the  IRP in the minifilter's callback data with the current thread.

## Syntax

````
NTSTATUS FltPropagateActivityIdToThread(
  _In_    PFLT_CALLBACK_DATA CallbackData,
  _Inout_ LPGUID             PropagatedId,
  _Out_   LPGUID             *OriginalId
);
````

## Parameters

`CallbackData`

A pointer to the callback data containing the request with an associated activity ID.

`PropagateId`

TBD

`OriginalId`

On return, the <b>GUID</b> pointer referenced by <i>OriginalId</i> points to the activity ID that was previously set for the thread.


## Return Value

<b>FltPropagateActivityIdToThread</b> returns one of the following <b>NTSTATUS</b> values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The callback data does not contain a request for an IRP operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request in <i>CallbackData</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
An activity ID was returned in the <b>GUID</b> value pointed to by <i>Guid</i>.

</td>
</tr>
</table>

## Remarks

The <b>FltPropagateActivityIdToThread</b> routine is  used by trace aware minifilters. A minifilter will use this routine to attach the activity ID from an IRP   to a worker thread processing I/O for the request.

    A minifilter must call <b>IoClearActivityIdThread</b> with the pointer in <i>OriginalId</i> before
    returning control from the worker thread if the call to <b>FltPropagateActivityIdToThread</b> was successful.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with  Windows 8.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetactivityidcallbackdata.md">FltGetActivityIdCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetactivityidcallbackdata.md">FltSetActivityIdCallbackData</a>