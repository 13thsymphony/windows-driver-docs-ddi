---
UID: NF.fcb.RxFinalizeSrvCall
title: RxFinalizeSrvCall
author: windows-driver-content
description: RxFinalizeSrvCall finalizes the given SRV_CALL structure. The caller must have an exclusive lock on the netname table associated with the device object.
old-location: ifsk\rxfinalizesrvcall.htm
old-project: ifsk
ms.assetid: 293bb629-ac31-4ae3-bba3-b06812e9e6cb
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RxFinalizeSrvCall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Mrxfcb.h, Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxFinalizeSrvCall
req.alt-loc: fcb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
---

# RxFinalizeSrvCall function



## -description
<p><b>RxFinalizeSrvCall</b> finalizes the given SRV_CALL structure. The caller must have an exclusive lock on the netname table associated with the device object. </p>


## -syntax

````
BOOLEAN RxFinalizeSrvCall(
  _Out_ PSRV_CALL ThisSrvCall,
  _In_  BOOLEAN   ForceFinalize
);
````


## -parameters
<dl>

### -param <i>ThisSrvCall</i> [out]

<dd>
<p>A pointer to the SRV_CALL structure to finalize.</p>
</dd>

### -param <i>ForceFinalize</i> [in]

<dd>
<p>The value indicating whether the finalization should be forced, regardless of the reference count. </p>
<p>If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the SRV_CALL structure pointed to by <i>ThisSrvCall</i> must be 1 for the SRV_CALL to be finalized. </p>
</dd>
</dl>

## -returns
<p><b>RxFinalizeSrvCall</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: </p>

## -remarks
<p>The <b>RxFinalizeSrvCall</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when the reference count on the SRV_CALL is decremented to 1. RDBSS also calls <b>RxFinalizeSrvCall</b> when the network mini-redirector driver is stopped or unloaded. </p>

<p>Before calling <b>RxFinalizeSrvCall</b>, a lock on the netname table associated with the device object must be acquired in exclusive mode. </p>

<p>If the current executing process ID is the same as the RDBSS process ID, then a delayed worker thread will be dispatched to destroy the SRV_CALL structure. This worker thread will later call the <b>MRxFinalizeSrvCall</b> routine provided by the network mini-redirector to finalize the SRV_CALL. Otherwise, the <b>MRxFinalizeSrvCall</b> routine will be called directly to finalize the SRV_CALL. </p>

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
<dt>Fcb.h (include Mrxfcb.h or Fcb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.mrxfinalizesrvcall">MRxFinalizeSrvCall</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>
</dt>
<dt>
<a href="ifsk.the_srv_call_structure">The SRV_CALL Structure</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeSrvCall function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
