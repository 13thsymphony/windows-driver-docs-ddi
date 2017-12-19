---
UID: NF.ksproxy.KsGetMediaTypeCount
title: KsGetMediaTypeCount function
author: windows-driver-content
description: The KsGetMediaTypeCount function returns the number of available media types on a pin factory identifier.
old-location: stream\ksgetmediatypecount.htm
old-project: stream
ms.assetid: 157cb12c-1b2d-45b5-8541-e16ee3449064
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsGetMediaTypeCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsGetMediaTypeCount
req.alt-loc: Ksproxy.lib,Ksproxy.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
---

# KsGetMediaTypeCount function



## -description
The <b>KsGetMediaTypeCount</b> function returns the number of available media types on a pin factory identifier.



## -syntax

````
HRESULT KsGetMediaTypeCount(
  _In_  HANDLE FilterHandle,
  _In_  ULONG  PinFactoryId,
  _Out_ ULONG  *MediaTypeCount
);
````


## -parameters

### -param FilterHandle [in]

Handle to the filter that contains the pin factory to query.


### -param PinFactoryId [in]

Identifier of the pin factory against which the number of media types is being returned.


### -param MediaTypeCount [out]

Pointer to a variable to receive the number of media types.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
The number of available media types that <b>KsGetMediaTypeCount</b> returns is equal to the number of available data ranges. 


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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ksproxy.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikspinfactory.md">IKsPinFactory</a>
</dt>
<dt>
<a href="stream.ksdatarange">KSDATARANGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetMediaTypeCount function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

