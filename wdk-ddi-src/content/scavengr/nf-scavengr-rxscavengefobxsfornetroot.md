---
UID: NF.scavengr.RxScavengeFobxsForNetRoot
title: RxScavengeFobxsForNetRoot
author: windows-driver-content
description: RxScavengeFobxsForNetRoot scavenges all of the FOBX structures associated with a given NET_ROOT structure.
old-location: ifsk\rxscavengefobxsfornetroot.htm
old-project: ifsk
ms.assetid: 2a2320e6-b114-4ea7-9f2f-27fd47fef770
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RxScavengeFobxsForNetRoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: scavengr.h
req.include-header: Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxScavengeFobxsForNetRoot
req.alt-loc: scavengr.h
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

# RxScavengeFobxsForNetRoot function



## -description
<p><b>RxScavengeFobxsForNetRoot</b> scavenges all of the FOBX structures associated with a given NET_ROOT structure.</p>


## -syntax

````
VOID RxScavengeFobxsForNetRoot(
   PNET_ROOT NetRoot,
   PFCB      PurgingFcb
);
````


## -parameters
<dl>

### -param <i>NetRoot</i> 

<dd>
<p>A pointer to the NET_ROOT structure for which the FOBX structures need to be scavenged.</p>
</dd>

### -param <i>PurgingFcb</i> 

<dd>
<p>A pointer to the FCB for which the scavenging should occur.</p>
</dd>
</dl>

## -returns
<p>None </p>

## -remarks
<p>At cleanup, there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by the memory manager and cache manager. On cleanup, the FOBX is put on a close pending list and removed from the corresponding list when a close operation is received. In the interim, if an open operation is failing with ACCESS_DENIED status, then RDBSS can force a purge and scavenge of the FOBX structure. This is a synchronous operation.</p>

<p>For directory renames, all files under the directory need to be closed. So, a network mini-redirector might call <b>RxPurgeRelatedFobxs</b> and <b>RxScavengeFobxsForNetRoot</b> in response to a IRP_MJ_SET_INFORMATION request to rename a directory. By passing in the NET_ROOT structure for the directory and a <b>NULL</b> FCB, all of the FOBX structures associated with the directory would be purged and scavenged.</p>

<p>The <b>RxScavengeFobxsForNetRoot</b> routine acquires the scavenger mutex, traverses the <b>FobxsToBeFinalized</b> list member of the scavenger object and adds any entries found to tail of the <b>ScavengerFinalizationList</b> member of the scavenger object, and then releases the mutex. </p>

<p>If <i>PurgingFcb </i>is not <b>NULL</b>, and this purging FCB structure is not the same as the FCB associated with the FOBX structure on the <b>FobxsToBeFinalized</b> list member of the scavenger object, <b>RxScavengeFobxsForNetRoot</b> will call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a> callback routine provided by the network mini-redirector if it is supported. The call to <b>MRxAreFilesAliased</b> is to determine if the PFCB is an alias for the FCB associated with the FOBX structure.</p>

<p>On checked builds, <b>RxScavengeAllFobxs</b> causes the system to ASSERT for the following condition:</p>

<p>The <b>NodeTypeCode</b> member of an FOBX structure is not RDBSS_NTC_FOBX.</p>

<p>At cleanup, there are no more user handles associated with the file object. In such cases, the time window between close and cleanup is dictated by the additional references maintained by the memory manager and cache manager. On cleanup, the FOBX is put on a close pending list and removed from the corresponding list when a close operation is received. In the interim, if an open operation is failing with ACCESS_DENIED status, then RDBSS can force a purge and scavenge of the FOBX structure. This is a synchronous operation.</p>

<p>For directory renames, all files under the directory need to be closed. So, a network mini-redirector might call <b>RxPurgeRelatedFobxs</b> and <b>RxScavengeFobxsForNetRoot</b> in response to a IRP_MJ_SET_INFORMATION request to rename a directory. By passing in the NET_ROOT structure for the directory and a <b>NULL</b> FCB, all of the FOBX structures associated with the directory would be purged and scavenged.</p>

<p>The <b>RxScavengeFobxsForNetRoot</b> routine acquires the scavenger mutex, traverses the <b>FobxsToBeFinalized</b> list member of the scavenger object and adds any entries found to tail of the <b>ScavengerFinalizationList</b> member of the scavenger object, and then releases the mutex. </p>

<p>If <i>PurgingFcb </i>is not <b>NULL</b>, and this purging FCB structure is not the same as the FCB associated with the FOBX structure on the <b>FobxsToBeFinalized</b> list member of the scavenger object, <b>RxScavengeFobxsForNetRoot</b> will call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a> callback routine provided by the network mini-redirector if it is supported. The call to <b>MRxAreFilesAliased</b> is to determine if the PFCB is an alias for the FCB associated with the FOBX structure.</p>

<p>On checked builds, <b>RxScavengeAllFobxs</b> causes the system to ASSERT for the following condition:</p>

<p>The <b>NodeTypeCode</b> member of an FOBX structure is not RDBSS_NTC_FOBX.</p>

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
<dt>Scavengr.h (include Rxprocs.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554673">RxPurgeAllFobxs</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554679">RxPurgeRelatedFobxs</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554707">RxScavengeAllFobxs</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxScavengeFobxsForNetRoot function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
