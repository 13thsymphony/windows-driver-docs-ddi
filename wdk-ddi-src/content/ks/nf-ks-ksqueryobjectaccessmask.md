---
UID: NF.ks.KsQueryObjectAccessMask
title: KsQueryObjectAccessMask function
author: windows-driver-content
description: The KsQueryObjectAccessMask function returns the access originally granted to the first client that created a handle on the associated object. Access cannot be changed by duplicating handles.
old-location: stream\ksqueryobjectaccessmask.htm
old-project: stream
ms.assetid: 7631baa9-6d5a-44b6-ac19-2b3ecaac9293
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsQueryObjectAccessMask
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
req.alt-api: KsQueryObjectAccessMask
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

# KsQueryObjectAccessMask function



## -description
The <b>KsQueryObjectAccessMask</b> function returns the access originally granted to the first client that created a handle on the associated object. Access cannot be changed by duplicating handles.



## -syntax

````
ACCESS_MASK KsQueryObjectAccessMask(
  _In_ KSOBJECT_HEADER Header
);
````


## -parameters

### -param Header [in]

Points to a header previously allocated by <b>KsAllocateObjectHeader</b> whose access-granted mask pointer is to be returned.


## -returns
The <b>KsQueryObjectAccessMask</b> function returns an access mask.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsQueryObjectAccessMask function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

