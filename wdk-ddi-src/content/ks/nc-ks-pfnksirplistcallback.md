---
UID: NC.ks.PFNKSIRPLISTCALLBACK
title: PFNKSIRPLISTCALLBACK
author: windows-driver-content
description: A streaming minidriver's KStrIrpListCallback routine is called to determine whether the passed in IRP should be moved from the source list to the destination list, or if IRP enumeration should be terminated.
old-location: stream\kstrirplistcallback.htm
old-project: stream
ms.assetid: acddecb5-f3e9-413e-a68c-91d71119e0f6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrIrpListCallback
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# PFNKSIRPLISTCALLBACK callback



## -description
A streaming minidriver's <i>KStrIrpListCallback</i> routine is called to determine whether the passed in IRP should be moved from the source list to the destination list, or if IRP enumeration should be terminated.



## -prototype

````
PFNKSIRPLISTCALLBACK KStrIrpListCallback;

NTSTATUS KStrIrpListCallback(
  _In_ PIRP  Irp,
  _In_ PVOID Context
)
{ ... }
````


## -parameters

### -param Irp [in]

Pointer to the IRP to possibly move to the destination list from the source list.


### -param Context [in]

Passed from <a href="stream.ksmoveirpsoncancelablequeue">KsMoveIrpsOnCancelableQueue</a>.


## -returns
Returns STATUS_SUCCESS to indicate the passed in IRP should be moved from the source list to the destination list. Returns STATUS_NO_MATCH if the passed in IRP should not be moved. Returns any other value to terminate enumeration.


## -remarks
<i>KStrIrpListCallback</i> is called at DISPATCH_LEVEL.

<i>KStrIrpListCallback</i> is always called at least once at the end of list processing with a <b>NULL</b> IRP value in order to complete list processing.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksmoveirpsoncancelablequeue">KsMoveIrpsOnCancelableQueue</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrIrpListCallback routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

