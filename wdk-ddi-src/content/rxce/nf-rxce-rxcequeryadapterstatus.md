---
UID : NF:rxce.RxCeQueryAdapterStatus
title : RxCeQueryAdapterStatus function
author : windows-driver-content
description : RxCeQueryAdapterStatus returns the ADAPTER_STATUS structure for a given transport in a caller-allocated buffer.
old-location : ifsk\rxcequeryadapterstatus.htm
old-project : ifsk
ms.assetid : ebe9bec3-6c38-48d8-b9af-03aadbc09d98
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : rxref_0813f428-95ae-47df-969c-c00563f3b3c8.xml, RxCeQueryAdapterStatus function [Installable File System Drivers], RxCeQueryAdapterStatus, rxce/RxCeQueryAdapterStatus, ifsk.rxcequeryadapterstatus
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : rxce.h
req.include-header : Rxce.h
req.target-type : Desktop
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : <= APC_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS"
req.product : Windows 10 or later.
---


# RxCeQueryAdapterStatus function
<b>RxCeQueryAdapterStatus</b> returns the ADAPTER_STATUS structure for a given transport in a caller-allocated buffer.

## Syntax

````
NTSTATUS RxCeQueryAdapterStatus(
   PRXCE_TRANSPORT        pTransport,
   struct _ADAPTER_STATUS *pAdapterStatus
);
````

## Parameters

`pTransport`

A pointer to the RDBSS transport that is associated with an adapter.

`pAdapterStatus`

On input, this parameter contains a pointer to caller-allocated buffer to hold the adapter status. On output when this call is successful, the buffer contains the adapter status associated with the specified RDBSS transport.


## Return Value

<b>RxCeQueryAdapterStatus</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ADDRESS_NOT_ASSOCIATED</b></dt>
</dl>
</td>
<td width="60%">
An adapter address is not associated with the RDBSS transport. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>pTransport</i> parameter passed to this routine was invalid. 

</td>
</tr>
</table>

## Remarks

<b>RxCeQueryAdapterStatus</b> returns an ADAPTER_STATUS structure for a given transport. This routine is most commonly used to get the NetBIOS name of the adapter. 

<b>RxCeQueryAdapterStatus</b> calls <b>TdiBuildQueryInformation</b> with a TDI_QUERY_ADAPTER_STATUS query.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rxce.h (include Rxce.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\rxce\nf-rxce-rxcequeryinformation.md">RxCeQueryInformation</a>

<a href="..\rxce\nf-rxce-rxcequerytransportinformation.md">RxCeQueryTransportInformation</a>

<a href="http://go.microsoft.com/fwlink/p/?linkid=138885">ADAPTER_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeQueryAdapterStatus function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>