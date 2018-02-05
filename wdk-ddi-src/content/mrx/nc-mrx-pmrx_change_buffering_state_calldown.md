---
UID : NC:mrx.PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
title : PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
author : windows-driver-content
description : TheMRxCompleteBufferingStateChangeRequest routine is called by RDBSS to notify the network mini-redirector that a buffering state change request has been completed.
old-location : ifsk\mrxcompletebufferingstatechangerequest.htm
old-project : ifsk
ms.assetid : 1484dcca-e29c-495d-917c-1debefc91409
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.mrxcompletebufferingstatechangerequest, MRxCompleteBufferingStateChangeRequest routine [Installable File System Drivers], MRxCompleteBufferingStateChangeRequest, PMRX_CHANGE_BUFFERING_STATE_CALLDOWN, PMRX_CHANGE_BUFFERING_STATE_CALLDOWN, mrx/MRxCompleteBufferingStateChangeRequest, mrxref_5ac31893-1998-454a-a0c9-07d32e60d8db.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : mrx.h
req.include-header : Mrx.h
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SetDSMCounters_IN, *PSetDSMCounters_IN
---


# PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback function
The<i>MRxCompleteBufferingStateChangeRequest</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to notify the network mini-redirector that a buffering state change request has been completed.

## Syntax

```
PMRX_CHANGE_BUFFERING_STATE_CALLDOWN PmrxChangeBufferingStateCalldown;

NTSTATUS PmrxChangeBufferingStateCalldown(
  IN OUT PRX_CONTEXT RxContext,
  IN OUT PMRX_SRV_OPEN SrvOpen,
  IN PVOID MRxContext
)
{...}
```

## Parameters

`RxContext`

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

`SrvOpen`

A pointer to a context parameter for use by the network mini-redirector callback routine.

`MRxContext`

A pointer to the SRV_OPEN structure and the associated FCB structure to be changed.


## Return Value

<i>MRxCompleteBufferingStateChangeRequest</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 
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
An option in the  buffering request change is not supported. 

</td>
</tr>
</table>

## Remarks

Before calling <i>MRxCompleteBufferingStateChangeRequest</i>, RDBSS:
<ul>
<li>
Acquires an exclusive lock on the FCB structure. 

</li>
<li>
Sets the <b>FcbState</b> member of <b>SrvOpen-&gt;Fcb</b> to FCB_STATE_BUFFERSTATE_CHANGING. 

</li>
<li>
Modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:<dl>
<dd>
<b>pRelevantSrvOpen</b> is set to the SRV_OPEN structure.

</dd>
<dd>
<b>pFcb</b> is set to the FCB structure.

</dd>
<dd>
<b>pFobx</b> is set to the FOBX structure.

</dd>
</dl>


</li>
</ul>If lock buffering is enabled, <i>MRxCompleteBufferingStateChangeRequest</i> will need to flush out the byte-range locks to the server. The list of locked regions is passed to the network mini-redirector in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure.

The Server Message Block (SMB) redirector uses <i>MRxCompleteBufferingStateChangeRequest</i> to send an oplock break response or to close the handle on an oplock break if the file is no longer in use. Byte range locks that need to be flushed out to the server are passed to the network mini-redirector in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure. The new oplock level is passed in the <i>MrxContext</i> parameter.

RDBSS ignores the return value from <i>MRxCompleteBufferingStateChangeRequest</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mrx.h (include Mrx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550687">MRxGetConnectionId</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549856">MRxComputeNewBufferingState</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxCompleteBufferingStateChangeRequest routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>