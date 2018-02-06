---
UID: NC:mrx.PMRX_GET_CONNECTION_ID
title: PMRX_GET_CONNECTION_ID
author: windows-driver-content
description: TheMRxGetConnectionId routine is called by RDBSS to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions.
old-location: ifsk\mrxgetconnectionid.htm
old-project: ifsk
ms.assetid: c994060c-d8b3-4daa-a0dd-a734ffe34229
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.mrxgetconnectionid, MRxGetConnectionId routine [Installable File System Drivers], MRxGetConnectionId, PMRX_GET_CONNECTION_ID, PMRX_GET_CONNECTION_ID, mrx/MRxGetConnectionId, mrxref_14943242-5da1-4404-bc5b-b86c2a88b347.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	mrx.h
apiname:
-	MRxGetConnectionId
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---


# PMRX_GET_CONNECTION_ID callback function
The<i>MRxGetConnectionId</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions.

## Syntax

```
PMRX_GET_CONNECTION_ID PmrxGetConnectionId;

NTSTATUS PmrxGetConnectionId(
  IN OUT PRX_CONTEXT RxContext,
  IN OUT PRX_CONNECTION_ID UniqueId
)
{...}
```

## Parameters

`RxContext`

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

`UniqueId`

A pointer to the connection ID when the routine returns.


## Return Value

<i>MRxGetConnectionId</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This routine is not implemented. 

</td>
</tr>
</table>

## Remarks

<i>MRxGetConnectionId</i> is called by RDBSS when trying to find or construct a V_NET_ROOT structure. 

If connection IDs are supported by the network mini-redirector, then the returned connection ID is appended to the NET_ROOT structure name stored in the NetName table used by RDBSS for storing network names. RDBSS considers the connection ID as an opaque blob, and does a byte-by-byte comparison of the connection ID blob while looking up the NetName table for a given name with a connection ID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mrx.h (include Mrx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549850">MRxCompleteBufferingStateChangeRequest</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549856">MRxComputeNewBufferingState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxGetConnectionId routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>