---
UID: NF.fcb.RxFinalizeNetFobx
title: RxFinalizeNetFobx
author: windows-driver-content
description: RxFinalizeNetFOBX finalizes the given FOBX structure. The caller must have an exclusive lock on the FCB associated with FOBX structure.
old-location: ifsk\rxfinalizenetfobx.htm
old-project: ifsk
ms.assetid: 052e7995-fab8-4863-a3a2-8b9bd6f21ec9
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RxFinalizeNetFobx
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
req.alt-api: RxFinalizeNetFobx
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

# RxFinalizeNetFobx function



## -description
<p><b>RxFinalizeNetFOBX</b> finalizes the given FOBX structure. The caller must have an exclusive lock on the FCB associated with FOBX structure. </p>


## -syntax

````
BOOLEAN RxFinalizeNetFobx(
  _Out_ PFOBX   ThisFobx,
  _In_  BOOLEAN RecursiveFinalize,
  _In_  BOOLEAN ForceFinalize
);
````


## -parameters
<dl>

### -param <i>ThisFobx</i> [out]

<dd>
<p>A pointer to the FOBX structure to finalize.</p>
</dd>

### -param <i>RecursiveFinalize</i> [in]

<dd>
<p>The value indicating whether the finalization should be done recursively. This parameter is not currently used.</p>
</dd>

### -param <i>ForceFinalize</i> [in]

<dd>
<p>The value indicating whether the finalization should be forced, regardless of the reference count. </p>
<p>If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the FOBX structure pointed to by <i>ThisFobx </i>must be 0 for the FOBX to be finalized. </p>
</dd>
</dl>

## -returns
<p><b>RxFinalizeNetFOBX</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: </p>

## -remarks
<p>The <b>RxFinalizeNetFOBX</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CLOSE. This IRP is normally received by RDBSS in response to a user-mode application requesting a file close operation. It is also possible for another kernel driver to issue such an IRP. </p>

<p>Before calling <b>RxFinalizeNetFOBX</b>, a lock on the FCB structure must be acquired in exclusive mode. </p>

<p>The <b>RxFinalizeNetFOBX</b> routine will call the <b>MRxDeallocateForFobx</b> routine provided by the network mini-redirector to free the memory for the FOBX if the network mini-redirector supports this routine. </p>

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
<a href="ifsk.the_fcb_structure">The FCB Structure</a>
</dt>
<dt>
<a href="ifsk.the_fobx_structure">The FOBX Structure</a>
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
<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>
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
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeNetFOBX function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
