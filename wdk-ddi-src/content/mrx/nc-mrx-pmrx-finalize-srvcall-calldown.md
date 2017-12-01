---
UID: NC.mrx.PMRX_FINALIZE_SRVCALL_CALLDOWN
title: PMRX_FINALIZE_SRVCALL_CALLDOWN
author: windows-driver-content
description: The MRxFinalizeSrvCall routine is called by RDBSS to request that a network mini-redirector finalize an SRV_CALL structure.
old-location: ifsk\mrxfinalizesrvcall.htm
old-project: ifsk
ms.assetid: f870334a-cf39-47a2-868a-f6fd7c3aee1c
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
req.alt-api: MRxFinalizeSrvCall
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

# PMRX_FINALIZE_SRVCALL_CALLDOWN callback



## -description
<p>The <i>MRxFinalizeSrvCall</i> routine is called by <a href="ifsk.the_rdbss_driver_and_library">RDBSS</a> to request that a network mini-redirector finalize an SRV_CALL structure. </p>


## -prototype

````
PMRX_FINALIZE_SRVCALL_CALLDOWN MRxFinalizeSrvCall;

NTSTATUS MRxFinalizeSrvCall(
  _Inout_ PMRX_SRV_CALL pSrvCall,
  _In_    BOOLEAN       Force
)
{ ... }
````


## -parameters
<dl>

### -param <i>pSrvCall</i> [in, out]

<dd>
<p>A pointer to the SRV_CALL structure to finalize. </p>
</dd>

### -param <i>Force</i> [in]

<dd>
<p>A pointer to a Boolean value that indicates if the disconnect is to be enforced immediately, ignoring the reference count on the SRV_CALL structure. The <i>Force</i> parameter is the <i>ForceFinalize</i> parameter passed to the <a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a> routine. This action triggers a call to <i>MRxFinalizeSrvCall</i>.</p>
</dd>
</dl>

## -returns
<p><i>MRxFinalizeSrvCall</i> returns STATUS_SUCCESS on success. </p>

## -remarks
<p><i>MRxFinalizeSrvCall</i> is called when RDBSS is tearing down an SRV_CALL structure. The network mini-redirector is expected to close its connection to the server. </p>

<p><i>MRxFinalizeSrvCall</i> is called by RDBSS after receiving an <a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a> call. If <a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a> is called from a different process than the RDBSS system process, then the call to <i>MRxFinalizeSrvCall</i> is posted to a worker thread for later execution. At some later time <b>RxFinalizeSrvCall</b> is called to complete the finalization of the SRV_CALL structure. </p>

<p>RDBSS ignores the return value from the <i>MRxFinalizeSrvCall</i> call. </p>

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
<a href="ifsk.mrxcreatesrvcall">MRxCreateSrvCall</a>
</dt>
<dt>
<a href="ifsk.mrxcreatevnetroot">MRxCreateVNetRoot</a>
</dt>
<dt>
<a href="ifsk.mrxextractnetrootname">MRxExtractNetRootName</a>
</dt>
<dt>
<a href="ifsk.mrxfinalizenetroot">MRxFinalizeNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>
</dt>
<dt>
<a href="ifsk.mrxfinalizevnetroot">MRxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="ifsk.mrxpreparsename">MRxPreparseName</a>
</dt>
<dt>
<a href="ifsk.mrxsrvcallwinnernotify">MRxSrvCallWinnerNotify</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MRxFinalizeSrvCall routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
