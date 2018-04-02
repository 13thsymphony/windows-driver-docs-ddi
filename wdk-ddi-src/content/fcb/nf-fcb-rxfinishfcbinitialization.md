---
UID: NF:fcb.RxFinishFcbInitialization
title: RxFinishFcbInitialization function
author: windows-driver-content
description: RxFinishFcbInitialization is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector.
old-location: ifsk\rxfinishfcbinitialization.htm
old-project: ifsk
ms.assetid: 290d0b06-ccf7-4792-b7bb-556092845e55
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RDBSS_NTC_MAILSLOT, RDBSS_NTC_SPOOLFILE, RDBSS_NTC_STORAGE_TYPE_DIRECTORY, RDBSS_NTC_STORAGE_TYPE_FILE, RDBSS_NTC_STORAGE_TYPE_UNKNOWN, RxFinishFcbInitialization, RxFinishFcbInitialization function [Installable File System Drivers], fcb/RxFinishFcbInitialization, ifsk.rxfinishfcbinitialization, rxref_436f96f7-35ed-484b-8963-4afa559d3cfb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Mrxfcb.h, Nodetype.h, Fcb.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxFinishFcbInitialization
product:
- Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---


# RxFinishFcbInitialization function
<b>RxFinishFcbInitialization</b> is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector.

## Syntax

```
void RxFinishFcbInitialization(
  IN OUT PMRX_FCB                Fcb,
  IN RX_FILE_TYPE                FileType,
  IN PFCB_INIT_PACKET InitPacket OPTIONAL
);
```

## Parameters

`Fcb`

TBD

`FileType`

TBD

`OPTIONAL`

TBD


## Return Value

None

## Remarks

When called as a result of an IRP_MJ_CREATE, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFCB</a> is called first to create the FCB. If the <b>Type</b> member of the NET_ROOT to be created is not a NET_ROOT_MAILSLOT, then <b>RxFinishFcbInitialization</b> is called to finish the initialization of the FCB structure. 

If the <b>FcbState</b> member of the MRX_FCB structure pointed to by <i>MrxFcb</i> does not have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET on, then the following members of the FCB will be updated from the <i>InitPacket</i> parameter if <i>InitPacket</i> is non <b>NULL</b>: <b>Attributes</b>, <b>NumberOfLinks</b>, <b>CreationTime</b>, <b>LastAccessTime</b>, <b>LastWriteTime</b>, <b>LastChangeTime</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize</b>, <b>Header.FileSize</b>, and <b>Header.ValidDataLength</b>. The FCB_STATE_TIME_AND_SIZE_ALREADY_SET option is then set on in the <b>FcbState</b> member of the FCB structure.

If the storage type is an RDBSS_NTC_MAILSLOT and the FcbState member of the FCB does have the FCB_STATE_TIME_AND_SIZE_ALREADY_SET option set on, then the following members of the FCB structure for the mail slot will be initialized to 0: <b>Attributes</b>, <b>NumberOfLinks</b>,<b> CreationTime.QuadPart</b>,<b> LastAccessTime.QuadPart</b>, <b>LastWriteTime.QuadPart</b>, <b>LastChangeTime</b>.<b>QuadPart</b>, <b>ActualAllocationLength</b>, <b>Header.AllocationSize.QuadPart</b>, <b>Header.FileSize.QuadPart</b>, and <b>Header.ValidDataLength.QuadPart</b>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | fcb.h (include Mrxfcb.h, Nodetype.h, Fcb.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFCB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554376">RxCreateSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554380">RxCreateVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554409">RxFinalizeConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554421">RxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554432">RxFinalizeSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554450">RxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554463">RxForceFinalizeAllVNetRoots</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554728">RxSetSrvCallDomainName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554608">RxpDereferenceNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554627">RxpReferenceNetFcb</a>