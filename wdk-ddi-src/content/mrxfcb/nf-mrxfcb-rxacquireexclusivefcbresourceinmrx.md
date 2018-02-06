---
UID: NF:mrxfcb.RxAcquireExclusiveFcbResourceInMRx
title: RxAcquireExclusiveFcbResourceInMRx function
author: windows-driver-content
description: RxAcquireExclusiveFcbResourceInMRx acquires the FCB resource for a network mini-redirector driver in exclusive mode.
old-location: ifsk\rxacquireexclusivefcbresourceinmrx.htm
old-project: ifsk
ms.assetid: 417c3ffd-5c40-430d-9aec-169203dba685
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxAcquireExclusiveFcbResourceInMRx routine [Installable File System Drivers], rxref_54a3508a-7d99-487a-9363-a13500540230.xml, ifsk.rxacquireexclusivefcbresourceinmrx, RxAcquireExclusiveFcbResourceInMRx, mrxfcb/RxAcquireExclusiveFcbResourceInMRx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrxfcb.h
req.include-header: Mrxfcb.h
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
-	mrxfcb.h
apiname:
-	RxAcquireExclusiveFcbResourceInMRx
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---


# RxAcquireExclusiveFcbResourceInMRx function
<b>RxAcquireExclusiveFcbResourceInMRx</b> acquires the FCB resource for a network mini-redirector driver in exclusive mode. This routine will wait for the FCB resource to be free if it was previously acquired and does not return control until the exclusive resource has been acquired.

## Syntax

````
NTSTATUS RxAcquireExclusiveFcbResourceInMRx(
  _Inout_ PMRX_FCB pFcb
);
````

## Parameters

`Fcb`

TBD


## Return Value

<b>RxAcquireExclusiveFcbResourceInMRx</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
The FCB resource was not acquired.

</td>
</tr>
</table>

## Remarks

The synchronization resources of interest to a network mini-redirector driver are primarily associated with the FCB. There is a paging I/O resource and a regular resource. The paging I/O resource is managed internally by RDBSS. The only resource accessible to a network mini-redirector driver is the regular resource which should be accessed using <b>RxAcquireExclusiveFcbResourceInMRx</b>, <b>RxAcquireExclusiveFcbResourceInMRxEx</b>, or <b>RxAcquireSharedFcbResourceInMRx</b>, depending on the acquired mode desired. 

<b>RxAcquireExclusiveFcbResourceInMRx</b> will wait for the FCB resource to be free if it was previously acquired  and does not return control until the exclusive resource has been acquired. This routine acquires the FCB resource even if the RX_CONTEXT associated with this FCB has been canceled.

An FCB resource acquired with <b>RxAcquireExclusiveFcbResourceInMRx </b>should be released by calling <b>RxReleaseFcbResourceInMRx</b> or <b>RxReleaseFcbResourceForThreadInMRx</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mrxfcb.h (include Mrxfcb.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>

<a href="..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrxex.md">RxAcquireSharedFcbResourceInMRxEx</a>

<a href="..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrx.md">RxAcquireSharedFcbResourceInMRx</a>

<a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceinmrx.md">RxReleaseFcbResourceInMRx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxAcquireExclusiveFcbResourceInMRx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>