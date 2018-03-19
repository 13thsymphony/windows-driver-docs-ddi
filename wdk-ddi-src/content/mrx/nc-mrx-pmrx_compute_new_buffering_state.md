---
UID: NC:mrx.PMRX_COMPUTE_NEW_BUFFERING_STATE
title: PMRX_COMPUTE_NEW_BUFFERING_STATE
author: windows-driver-content
description: TheMRxComputeNewBufferingState routine is called by RDBSS to request that the network mini-redirector compute a new buffering state change.
old-location: ifsk\mrxcomputenewbufferingstate.htm
old-project: ifsk
ms.assetid: d47cbcab-8682-4c7f-b651-3d1e0f78dc0c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MRxComputeNewBufferingState, MRxComputeNewBufferingState routine [Installable File System Drivers], PMRX_COMPUTE_NEW_BUFFERING_STATE, ifsk.mrxcomputenewbufferingstate, mrx/MRxComputeNewBufferingState, mrxref_294ad2d0-2454-437d-818a-6879361f97e5.xml
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
-	MRxComputeNewBufferingState
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---


# PMRX_COMPUTE_NEW_BUFFERING_STATE callback function
The<i>MRxComputeNewBufferingState</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector compute a new buffering state change.

## Syntax

```
PMRX_COMPUTE_NEW_BUFFERING_STATE PmrxComputeNewBufferingState;

NTSTATUS PmrxComputeNewBufferingState(
  IN OUT PMRX_SRV_OPEN SrvOpen,
  IN PVOID MRxContext,
  OUT PULONG NewBufferingState
)
{...}
```

## Parameters

`SrvOpen`

A pointer to the SRV_OPEN structure and the associated FCB structure.

`MRxContext`

A pointer to a context parameter for use by the network mini-redirector callback.

`NewBufferingState`

A pointer to where the new buffering state is stored when the routine returns.


## Return Value

<i>MRxComputeNewBufferingState</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

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
A feature that is requested is not supported. 

</td>
</tr>
</table>

## Remarks

Before calling <i>MRxComputeNewBufferingState</i>, RDBSS sets the <b>FcbState</b> member of <i>SrvOpen</i><i>-&gt;Fcb</i> to FCB_STATE_BUFFERSTATE_CHANGING. 

The Server Message Block (SMB) redirector uses <i>MRxComputeNewBufferingState</i> to map the SMB-specific oplock levels into the appropriate RDBSS buffering state flags. The oplock level is passed in the <i>MrxContext</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mrx.h (include Mrx.h) |

## See Also

<a href="..\mrx\nc-mrx-pmrx_get_connection_id.md">MRxGetConnectionId</a>



<a href="..\mrx\nc-mrx-pmrx_change_buffering_state_calldown.md">MRxCompleteBufferingStateChangeRequest</a>