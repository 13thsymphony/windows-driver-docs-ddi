---
UID: NF:fcb.RxCreateNetRoot
title: RxCreateNetRoot function
author: windows-driver-content
description: RxCreateNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.
old-location: ifsk\rxcreatenetroot.htm
old-project: ifsk
ms.assetid: 076624d3-96f5-4e93-8598-b880a6b2289b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fcb/RxCreateNetRoot, rxref_3171aa4b-bf5b-4114-a5a0-40af765b09da.xml, RxCreateNetRoot function [Installable File System Drivers], ifsk.rxcreatenetroot, RxCreateNetRoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, Fcb.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fcb.h
apiname:
-	RxCreateNetRoot
product: Windows
targetos: Windows
req.typenames: "*PFA_ENTRY, FA_ENTRY"
---


# RxCreateNetRoot function
<b>RxCreateNetRoot</b> allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.

## Syntax

````
PNET_ROOT RxCreateNetRoot(
  _In_     PSRV_CALL         SrvCall,
  _In_     PUNICODE_STRING   Name,
  _In_     ULONG             NetRootFlags,
  _In_opt_ PRX_CONNECTION_ID RxConnectionId
);
````

## Parameters

`SrvCall`

A pointer to the associated SRV_CALL structure.

`Name`

A pointer to the name to be inserted in the name table.

`NetRootFlags`

The value to set the <b>Flags</b> member of the NET_ROOT which is used to denote the state of the NET_ROOT structure.

`RxConnectionId`

A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the prefix name table.


## Return Value

<b>RxCreateNetRoot</b> returns a pointer to a newly created NET_ROOT data structure on success or a <b>NULL</b> pointer on failure.

## Remarks

The <b>RxCreateNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a NET_ROOT needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateNetRoot</b>, a lock on the name table associated with the device object member of the <i>SrvCall</i> parameter must be acquired in exclusive mode. 

The NET_ROOT flags are split into two groups, those visible to network mini redirectors and those invisible to network mini redirectors. The visible ones are the lower 16-bits of the <b>Flags</b> member of the NET_ROOT. This routine does not check or test which flags are being set. 

On success, the reference count for the SRV_CALL structure is incremented.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | fcb.h (include Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, Fcb.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



<a href="https://msdn.microsoft.com/9a3bb194-0289-47f4-a5c8-848d8d82cdd7">The SRV_CALL Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateNetRoot function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>