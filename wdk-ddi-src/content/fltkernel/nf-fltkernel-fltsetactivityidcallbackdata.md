---
UID : NF:fltkernel.FltSetActivityIdCallbackData
title : FltSetActivityIdCallbackData function
author : windows-driver-content
description : The FltSetActivityIdCallbackData routine sets the a activity ID for an IRP in a minifilter's callback data.
old-location : ifsk\fltsetactivityidcallbackdata.htm
old-project : ifsk
ms.assetid : D7CA9DAB-E350-42D5-A008-5CC12D5313D3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.fltsetactivityidcallbackdata, FltSetActivityIdCallbackData, fltkernel/FltSetActivityIdCallbackData, FltSetActivityIdCallbackData routine [Installable File System Drivers]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with  Windows 8.
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
req.lib : FltMgr.lib
req.dll : Fltmgr.sys
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltSetActivityIdCallbackData function
The <b>FltSetActivityIdCallbackData</b> routine sets the a activity ID for an IRP in a minifilter's callback data.

## Syntax

````
NTSTATUS FltSetActivityIdCallbackData(
  _Inout_  PFLT_CALLBACK_DATA CallbackData,
  _In_opt_ LPGUID             Guid
);
````

## Parameters

`CallbackData`

A pointer to the callback data containing the request with an associated activity ID.

`Guid`

A optional pointer to the <b>GUID</b> structure receiving the activity ID. if <i>Guid</i> is <b>NULL</b>, the system will attempt to assign an ETW activity ID for the request.


## Return Value

<b>FltSetActivityIdCallbackData</b> returns one of the following <b>NTSTATUS</b> values.
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

-or-

The <b>GUID</b> pointed to by <i>Guid</i> is was not provided and no ETW activity ID is available or the operation.

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
An activity ID pointed to by <i>Guid</i> was set for the IRP in <i>CallbackData</i>.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetactivityidcallbackdata.md">FltGetActivityIdCallbackData</a>

<a href="..\fltkernel\nf-fltkernel-fltpropagateactivityidtothread.md">FltPropagateActivityIdToThread</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetActivityIdCallbackData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>