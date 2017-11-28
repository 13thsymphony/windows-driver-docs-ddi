---
UID: NF.ks.KsMoveIrpsOnCancelableQueue
title: KsMoveIrpsOnCancelableQueue
author: windows-driver-content
description: The KsMoveIrpsOnCancelableQueue function moves the specified IRPs from the SourceList parameter to the DestinationList parameter depending on the value returned from the minidriver-defined KStrIrpListCallback function.
old-location: stream\ksmoveirpsoncancelablequeue.htm
old-project: stream
ms.assetid: 1f6b4d93-fca8-40da-b87e-c95169f142ea
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: KsMoveIrpsOnCancelableQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsMoveIrpsOnCancelableQueue
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
req.iface: 
---

# KsMoveIrpsOnCancelableQueue function



## -description
<p>The <b>KsMoveIrpsOnCancelableQueue</b> function moves the specified IRPs from the <i>SourceList</i> parameter to the <i>DestinationList </i>parameter depending on the value returned from the minidriver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567187">KStrIrpListCallback</a> function.</p>


## -syntax

````
NTSTATUS KsMoveIrpsOnCancelableQueue(
  _Inout_  PLIST_ENTRY           SourceList,
  _In_     PKSPIN_LOCK           SourceLock,
  _Inout_  PLIST_ENTRY           DestinationList,
  _In_opt_ PKSPIN_LOCK           DestinationLock,
  _In_     KSLIST_ENTRY_LOCATION ListLocation,
  _In_     PFNKSIRPLISTCALLBACK  ListCallback ,
  _In_     PVOID                 Context 
);
````


## -parameters
<dl>

### -param <i>SourceList</i> [in, out]

<dd>
<p>Specifies the head of the queue from which to remove the IRPs.</p>
</dd>

### -param <i>SourceLock</i> [in]

<dd>
<p>Pointer to the driver's spin lock for source queue access.</p>
</dd>

### -param <i>DestinationList</i> [in, out]

<dd>
<p>Specifies the head of the queue on which to add the IRPs.</p>
</dd>

### -param <i>DestinationLock</i> [in, optional]

<dd>
<p>Optionally contains a pointer to driver's spin lock for destination queue access. If this is not provided, the <i>SourceLock</i> parameter is assumed to control both queues. If provided, this lock is always acquired after the <i>SourceLock</i> parameter. If the destination list has a separate spin lock, the system-wide Cancel Spin Lock is first acquired in order to move IRPs and allow the KSQUEUE_SPINLOCK_IRP_STORAGE() spin lock to be updated.</p>
</dd>

### -param <i>ListLocation</i> [in]

<dd>
<p>Indicates whether the IRPs should be enumerated from the head or the tail of the source queue. Any IRPs that are moved are placed on the destination queue's opposite end so that ordering is maintained.</p>
</dd>

### -param <i>ListCallback </i> [in]

<dd>
<p>Specifies the minidriver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff567187">KStrIrpListCallback</a> function to call to indicate whether a specific IRP should be moved from <i>SourceList</i> to <i>DestinationList</i>, or if enumeration should be terminated.</p>
</dd>

### -param <i>Context </i> [in]

<dd>
<p>Context passed to <i>ListCallback</i>.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if the list was completely enumerated; otherwise, returns any warning or error returned by the minidriver-defined <i>KStrIrpListCallback</i> callback function that interrupted enumeration.</p>

## -remarks
<p>An IRP is moved if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567187">KStrIrpListCallback</a> function indicates that it should be moved, whether it is currently acquired. If <i>KStrIrpListCallback </i>returns STATUS_SUCCESS, the IRP is moved. If it returns STATUS_NO_MATCH, the IRP is not moved. Any other return warning or error value will terminate enumeration and be returned by the function. The STATUS_NO_MATCH value should not be returned as an error by <i>KStrIrpListCallback</i>. <i>KStrIrpListCallback</i> is called at DISPATCH_LEVEL. <i>KStrIrpListCallback</i> is always called at least once at the end with a <b>NULL</b> IRP value to complete list enumeration.</p>

<p><b>KsMoveIrpsOnCancelableQueue</b> continues through the list until the callback function indicates that the search should be terminated, or the end of the list is reached. <b>KsMoveIrpsOnCancelableQueue</b> minimizes the use of the system-wide Cancel Spin Lock by using the provided spin locks to synchronize access when possible. <b>KsMoveIrpsOnCancelableQueue</b> does not allow the cancel routine to be modified while moving IRPs.</p>

<p>The function can be called at DISPATCH_LEVEL or lower.</p>

<p>An IRP is moved if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567187">KStrIrpListCallback</a> function indicates that it should be moved, whether it is currently acquired. If <i>KStrIrpListCallback </i>returns STATUS_SUCCESS, the IRP is moved. If it returns STATUS_NO_MATCH, the IRP is not moved. Any other return warning or error value will terminate enumeration and be returned by the function. The STATUS_NO_MATCH value should not be returned as an error by <i>KStrIrpListCallback</i>. <i>KStrIrpListCallback</i> is called at DISPATCH_LEVEL. <i>KStrIrpListCallback</i> is always called at least once at the end with a <b>NULL</b> IRP value to complete list enumeration.</p>

<p><b>KsMoveIrpsOnCancelableQueue</b> continues through the list until the callback function indicates that the search should be terminated, or the end of the list is reached. <b>KsMoveIrpsOnCancelableQueue</b> minimizes the use of the system-wide Cancel Spin Lock by using the provided spin locks to synchronize access when possible. <b>KsMoveIrpsOnCancelableQueue</b> does not allow the cancel routine to be modified while moving IRPs.</p>

<p>The function can be called at DISPATCH_LEVEL or lower.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567187">KStrIrpListCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsMoveIrpsOnCancelableQueue function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
