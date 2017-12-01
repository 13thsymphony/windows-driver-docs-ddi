---
UID: NF.rxprocs.RxFinalizeNetFcb
title: RxFinalizeNetFcb
author: windows-driver-content
description: RxFinalizeNetFCB finalizes the given FCB structure. The caller must have an exclusive lock on the NET_ROOT associated with FCB.
old-location: ifsk\rxfinalizenetfcb.htm
old-project: ifsk
ms.assetid: 1eed44e2-f9ed-45a1-a5fa-dbf6a9c7c703
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RxFinalizeNetFcb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxFinalizeNetFcb
req.alt-loc: rxprocs.h
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
req.product: Windows 10 or later.
---

# RxFinalizeNetFcb function



## -description
<p><b>RxFinalizeNetFCB</b> finalizes the given FCB structure. The caller must have an exclusive lock on the NET_ROOT associated with FCB. </p>


## -syntax

````
BOOLEAN RxFinalizeNetFcb(
  _Out_ PFCB    ThisFcb,
  _In_  BOOLEAN RecursiveFinalize,
  _In_  BOOLEAN ForceFinalize,
  _In_  LONG    ReferenceCount
);
````


## -parameters
<dl>

### -param <i>ThisFcb</i> [out]

<dd>
<p>A pointer to the FCB structure to finalize.</p>
</dd>

### -param <i>RecursiveFinalize</i> [in]

<dd>
<p>The value indicating whether the finalization should be done recursively. </p>
</dd>

### -param <i>ForceFinalize</i> [in]

<dd>
<p>The value indicating whether the finalization should be forced, regardless of the reference count. </p>
<p>If this parameter is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the FCB must be 1 for the FCB to be finalized. </p>
</dd>

### -param <i>ReferenceCount</i> [in]

<dd>
<p>The reference count on the FCB that will still allow forced finalization.</p>
</dd>
</dl>

## -returns
<p><b>RxFinalizeNetFCB</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: </p>

## -remarks
<p>The <b>RxFinalizeNetFCB</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CLOSE. This IRP is normally received by RDBSS in response to a user-mode application requesting a file close operation. It is also possible for another kernel driver to issue such an IRP. </p>

<p>The close handling strategy in RDBSS is predicated upon the axiom that the workload on the server should be minimized as and when possible. There are a number of applications which repeatedly close and open the same file (batch file processing, for example). In these cases the same file is opened, a line from a buffer is read, the file is closed and the same set of operations are repeated over and over again.</p>

<p>This is handled in RDBSS by a delayed processing of the close request. There is a delay of about 10 seconds between completing the request and initiating processing on the close request. This opens up a window during which a subsequent open operation can be collapsed onto an existing SRV_OPEN. The time interval can be tuned to meet these requirements.</p>

<p>Before calling <b>RxFinalizeNetFCB</b>, a lock on the FCB structure must be acquired in exclusive mode. </p>

<p>If the <i>RecursiveFinalize </i>parameter is <b>FALSE</b>, then <b>RxFinalizeNetFCB</b> will fail if there are outstanding references to the FCB (the <b>OpenCount</b> or <b>CleanCount</b> members of the FCB structureare non zero).</p>

<p>If the <i>ForceFinalize </i>parameter is <b>TRUE</b>, <b>RxFinalizeNetFCB</b> causes the system to ASSERT on checked builds. </p>

<p>After recursive finalization, the reference count associated with the FCB could be at most 1 for further finalization to occur. This final reference count belongs to the prefix name table of the NET_ROOT. The actual finalization is divided into two parts:</p>

<p>if the reference count equals 1 or the <i>ForceFinalize</i> parameter was <b>TRUE</b>, <b>RxFinalizeNetFCB</b> finalizes the FCB.</p>

<p>if the reference count goes to zero, the FCB is finalized and the memory used for the FCB is also released.</p>

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
<dt>Rxprocs.h (include Rxprocs.h)</dt>
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
<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeNetFCB function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
