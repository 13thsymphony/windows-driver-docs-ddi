---
UID: NF.ntddk.PsDetachSiloFromCurrentThread
title: PsDetachSiloFromCurrentThread function
author: windows-driver-content
description: This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the PsAttachSiloToCurrentThread routine.
old-location: kernel\psdetachsilofromcurrentthread.htm
old-project: kernel
ms.assetid: E364130B-9709-4FD9-8654-9FBC52E29145
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PsDetachSiloFromCurrentThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsDetachSiloFromCurrentThread
req.alt-loc: ntddk.h
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

# PsDetachSiloFromCurrentThread function



## -description
This routine removes a thread from a silo which was added by an attach. For more info about attaching, see the  <a href="kernel.psattachsilotocurrentthread">PsAttachSiloToCurrentThread</a> routine.


<div class="alert"><b>Note</b>  The caller is responsible for dereferencing the object after the detach has completed.</div>
<div> </div>



## -syntax

````
void PsDetachSiloFromCurrentThread(
  _In_ PESILO PreviousSilo
);
````


## -parameters

### -param PreviousSilo [in]

The value returned from the silo attach call.

## -returns
This routine does not return a value.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10, version 1607
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.psattachsilotocurrentthread">PsAttachSiloToCurrentThread</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsDetachSiloFromCurrentThread routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
