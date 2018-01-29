---
UID : NF:fcb.RxFinalizeNetFobx
title : RxFinalizeNetFobx function
author : windows-driver-content
description : RxFinalizeNetFOBX finalizes the given FOBX structure. The caller must have an exclusive lock on the FCB associated with FOBX structure.
old-location : ifsk\rxfinalizenetfobx.htm
old-project : ifsk
ms.assetid : 052e7995-fab8-4863-a3a2-8b9bd6f21ec9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : rxref_72a759e2-f9e6-44ce-b561-cb968b668a6f.xml, ifsk.rxfinalizenetfobx, fcb/RxFinalizeNetFobx, RxFinalizeNetFobx, RxFinalizeNetFobx function [Installable File System Drivers]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fcb.h
req.include-header : Mrxfcb.h, Fcb.h
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : <= APC_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : FA_ENTRY, *PFA_ENTRY
---


# RxFinalizeNetFobx function
<b>RxFinalizeNetFOBX</b> finalizes the given FOBX structure. The caller must have an exclusive lock on the FCB associated with FOBX structure.

## Syntax

````
BOOLEAN RxFinalizeNetFobx(
  _Out_ PFOBX   ThisFobx,
  _In_  BOOLEAN RecursiveFinalize,
  _In_  BOOLEAN ForceFinalize
);
````

## Parameters

`ThisFobx`

A pointer to the FOBX structure to finalize.

`RecursiveFinalize`

The value indicating whether the finalization should be done recursively. This parameter is not currently used.

`ForceFinalize`

The value indicating whether the finalization should be forced, regardless of the reference count. 

If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the FOBX structure pointed to by <i>ThisFobx </i>must be 0 for the FOBX to be finalized.


## Return Value

<b>RxFinalizeNetFOBX</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur:

## Remarks

The <b>RxFinalizeNetFOBX</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CLOSE. This IRP is normally received by RDBSS in response to a user-mode application requesting a file close operation. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxFinalizeNetFOBX</b>, a lock on the FCB structure must be acquired in exclusive mode. 

The <b>RxFinalizeNetFOBX</b> routine will call the <b>MRxDeallocateForFobx</b> routine provided by the network mini-redirector to free the memory for the FOBX if the network mini-redirector supports this routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fcb.h (include Mrxfcb.h, Fcb.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>

<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>

<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fobx-structure">The FOBX Structure</a>

<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>

<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>

<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>

<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>

<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>

<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>

<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>

<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>

<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>

<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>

<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>

<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeNetFOBX function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>