---
UID: NF.ks.KsFreeObjectHeader
title: KsFreeObjectHeader function
author: windows-driver-content
description: The KsFreeObjectHeader function cleans up and frees a previously allocated object header.
old-location: stream\ksfreeobjectheader.htm
old-project: stream
ms.assetid: 59ca5035-f4d8-4a9c-a298-c8dca604f4db
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsFreeObjectHeader
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
req.alt-api: KsFreeObjectHeader
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
---

# KsFreeObjectHeader function



## -description
The <b>KsFreeObjectHeader</b> function cleans up and frees a previously allocated object header.


## -syntax

````
VOID KsFreeObjectHeader(
  _In_ KSOBJECT_HEADER Header
);
````


## -parameters

### -param Header [in]

Points to the object header to free.

## -returns
None

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
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
<tr>
<th width="30%">
Library
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
<a href="stream.ksallocateobjectheader">KsAllocateObjectHeader</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFreeObjectHeader function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
