---
UID : NF:fcb.RxCreateNetFobx
title : RxCreateNetFobx function
author : windows-driver-content
description : RxCreateNetFobx allocates, initializes, and inserts a new file object extension (FOBX) structure into the in-memory data structures for a FCB that this FOBX is being opened on.
old-location : ifsk\rxcreatenetfobx.htm
old-project : ifsk
ms.assetid : 4ea03ea5-31df-4220-982c-0102d20c2d4a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RxCreateNetFobx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fcb.h
req.include-header : Rxcontx.h, Mrxfcb.h, Fcb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RxCreateNetFobx
req.alt-loc : fcb.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= APC_LEVEL
req.typenames : FA_ENTRY, *PFA_ENTRY
---


# RxCreateNetFobx function
<b>RxCreateNetFobx</b> allocates, initializes, and inserts a new file object extension (FOBX) structure into the in-memory data structures for a FCB that this FOBX is being opened on.

## Syntax

````
PMRX_FOBX RxCreateNetFobx(
  _Out_ PRX_CONTEXT   RxContext,
  _In_  PMRX_SRV_OPEN MrxSrvOpen
);
````

## Parameters

`RxContext`

A pointer to the RX_CONTEXT structure describing a create operation.

`MrxSrvOpen`

A pointer to the associated SRV_OPEN structure.


## Return Value

<b>RxCreateNetFobx</b> returns a pointer to a newly allocated FOBX data structure on success or a <b>NULL</b> pointer on failure.

## Remarks

Network mini-redirectors should call <b>RxCreateNetFobx</b> to create an FOBX at the end of a successful create operation.

Before calling <b>RxCreateNetFobx</b>, the FCB associated with the FOBX structure must be acquired in exclusive mode. 

<b>RxCreateNetFobx </b>will try and use the FOBX allocated as part of the associated FCB structure if it is available. If the FOBX allocated with the FCB is not available, then <b>RxCreateNetFobx </b>will try and use the FOBX allocated as part of the associated SRV_OPEN structure if it is available. In either of these cases, <b>RxCreateNetFobx</b> only needs to initialize the existing FOBX structure, no memory allocation is required. If both of the FOBX structures on the associated FCB and SRV_OPEN structure are not available, then <b>RxCreateNetFobx</b> will allocate a new FOBX structure. 

If the associated FCB is a paging file, <b>RxCreateNetFobx</b> allocates non-paged pool memory when creating the new FOBX data structure. If the associated FCB is a not a paging file, <b>RxCreateNetFobx</b> allocates paged pool memory when creating the new FOBX data structure.

Windows does not currently allow having a paging file on a remote machine.

On success, the following FOBX members in the FOBX structure are set:

The <b>NodeReference</b> member is set to 1.

The <b>FobxSerialNumber</b> member is set to 0.

The <b>SrvOpen</b> member is set to the associated SRV_OPEN structure.

The <b>fOpenCountDecremented</b> member is set to <b>FALSE</b>.

The <b>Flags</b> member is set to a value based on parameters from the RX_CONTEXT and whether a new FOBX needed to be allocated. 

On success, the reference count for the SRV_OPEN structure is incremented and the <b>NumberOfFobxs</b> member on the associated V_NET_ROOT structure is incremented.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fcb.h (include Rxcontx.h, Mrxfcb.h, Fcb.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>
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
<dt>
<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateNetFobx function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>