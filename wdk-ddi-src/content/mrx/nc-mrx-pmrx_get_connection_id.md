---
UID: NC:mrx.PMRX_GET_CONNECTION_ID
title: PMRX_GET_CONNECTION_ID
author: windows-driver-content
description: TheMRxGetConnectionId routine is called by RDBSS to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions.
old-location: ifsk\mrxgetconnectionid.htm
old-project: ifsk
ms.assetid: c994060c-d8b3-4daa-a0dd-a734ffe34229
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MRxGetConnectionId, MRxGetConnectionId routine [Installable File System Drivers], PMRX_GET_CONNECTION_ID, ifsk.mrxgetconnectionid, mrx/MRxGetConnectionId, mrxref_14943242-5da1-4404-bc5b-b86c2a88b347.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
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

<a href="..\mrx\nc-mrx-pmrx_change_buffering_state_calldown.md">MRxCompleteBufferingStateChangeRequest</a>



<a href="..\mrx\nc-mrx-pmrx_compute_new_buffering_state.md">MRxComputeNewBufferingState</a>