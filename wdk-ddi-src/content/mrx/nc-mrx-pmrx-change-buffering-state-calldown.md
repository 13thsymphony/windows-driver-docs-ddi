---
UID: NC.mrx.PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
title: PMRX_CHANGE_BUFFERING_STATE_CALLDOWN
author: windows-driver-content
description: TheMRxCompleteBufferingStateChangeRequest routine is called by RDBSS to notify the network mini-redirector that a buffering state change request has been completed.
old-location: ifsk\mrxcompletebufferingstatechangerequest.htm
old-project: ifsk
ms.assetid: 1484dcca-e29c-495d-917c-1debefc91409
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SetDSMCounters_IN, SetDSMCounters_IN, *PSetDSMCounters_IN
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
req.alt-api: MRxCompleteBufferingStateChangeRequest
req.alt-loc: mrx.h
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
req.iface: 
---

# PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback



## -description
<p>The<i>MRxCompleteBufferingStateChangeRequest</i> routine is called by <a href="ifsk.the_rdbss_driver_and_library">RDBSS</a> to notify the network mini-redirector that a buffering state change request has been completed. </p>


## -prototype

````
PMRX_CHANGE_BUFFERING_STATE_CALLDOWN MRxCompleteBufferingStateChangeRequest;

NTSTATUS MRxCompleteBufferingStateChangeRequest(
  _Inout_ PRX_CONTEXT   RxContext,
  _Inout_ PMRX_SRV_OPEN  SrvOpen,
  _In_    PVOID          MRxContext
)
{ ... }
````


## -parameters
<dl>

### -param <i>RxContext</i> [in, out]

<dd>
<p>A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.</p>
</dd>

### -param <i> SrvOpen</i> [in, out]

<dd>
<p>A pointer to a context parameter for use by the network mini-redirector callback routine.</p>
</dd>

### -param <i> MRxContext</i> [in]

<dd>
<p>A pointer to the SRV_OPEN structure and the associated FCB structure to be changed.</p>
</dd>
</dl>

## -returns
<p><i>MRxCompleteBufferingStateChangeRequest</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: </p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>An option in the  buffering request change is not supported. </p>

<p> </p>

## -remarks
<p>Before calling <i>MRxCompleteBufferingStateChangeRequest</i>, RDBSS:</p>

<p>Acquires an exclusive lock on the FCB structure. </p>

<p>Sets the <b>FcbState</b> member of <b>SrvOpen-&gt;Fcb</b> to FCB_STATE_BUFFERSTATE_CHANGING. </p>

<p>Modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:<dl>
<dd>
<p><b>pRelevantSrvOpen</b> is set to the SRV_OPEN structure.</p>
</dd>
<dd>
<p><b>pFcb</b> is set to the FCB structure.</p>
</dd>
<dd>
<p><b>pFobx</b> is set to the FOBX structure.</p>
</dd>
</dl>
</p>

<p><b>pRelevantSrvOpen</b> is set to the SRV_OPEN structure.</p>

<p><b>pFcb</b> is set to the FCB structure.</p>

<p><b>pFobx</b> is set to the FOBX structure.</p>

<p>If lock buffering is enabled, <i>MRxCompleteBufferingStateChangeRequest</i> will need to flush out the byte-range locks to the server. The list of locked regions is passed to the network mini-redirector in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure.</p>

<p>The Server Message Block (SMB) redirector uses <i>MRxCompleteBufferingStateChangeRequest</i> to send an oplock break response or to close the handle on an oplock break if the file is no longer in use. Byte range locks that need to be flushed out to the server are passed to the network mini-redirector in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure. The new oplock level is passed in the <i>MrxContext</i> parameter.</p>

<p>RDBSS ignores the return value from <i>MRxCompleteBufferingStateChangeRequest</i>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Mrx.h (include Mrx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.mrxcomputenewbufferingstate">MRxComputeNewBufferingState</a>
</dt>
<dt>
<a href="ifsk.mrxgetconnectionid">MRxGetConnectionId</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxCompleteBufferingStateChangeRequest routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
