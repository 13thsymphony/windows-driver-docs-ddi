---
UID: NF:ksproxy.IKsPin.KsPeekAllocator
title: IKsPin::KsPeekAllocator method
author: windows-driver-content
description: The KsPeekAllocator method returns a pointer to an IMemAllocator interface for a pin's assigned allocator.
old-location: stream\ikspin_kspeekallocator.htm
old-project: stream
ms.assetid: fd833d0b-2f81-4002-8280-38e17e528af6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsPin, IKsPin::KsPeekAllocator, KsPeekAllocator
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsPin.KsPeekAllocator
req.alt-loc: ksproxy.h
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
req.typenames: PIPE_STATE
---

# IKsPin::KsPeekAllocator method



## -description
The <b>KsPeekAllocator</b> method returns a pointer to an <b>IMemAllocator</b> interface for a pin's assigned allocator.



## -syntax

````
IMemAllocator* KsPeekAllocator(
  [in] KSPEEKOPERATION Operation
);
````


## -parameters

### -param Operation [in]

A value that specifies the type of operation. This value can be one of the following values from the KSPEEKOPERATION enumerated type.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsPeekOperation_PeekOnly</b>

</td>
<td>
<b>IKsPin::KsPeekAllocator </b>does not increment the reference count for the allocator. 

</td>
</tr>
<tr>
<td>
<b>KsPeekOperation_AddRef</b>

</td>
<td>
<b>IKsPin::KsPeekAllocator</b> increments the reference count for the allocator (calls AddRef). 

</td>
</tr>
</table>
 


## -returns
Returns a pointer to an <b>IMemAllocator</b> interface if successful; otherwise, returns <b>NULL</b>. 


## -remarks
For more information about <b>IMemAllocator</b>, see the Microsoft Windows SDK documentation.

This method is for proxy use and is not recommended for application use.


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
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikspin.md">IKsPin</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsPeekAllocator method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

