---
UID: NF.ksproxy.KsResolveRequiredAttributes
title: KsResolveRequiredAttributes function
author: windows-driver-content
description: The KsResolveRequiredAttributes function searches the attributes list that is attached to a data range for specified attributes and ensures that all specified attributes were found.
old-location: stream\ksresolverequiredattributes.htm
old-project: stream
ms.assetid: 04153845-4170-40db-ba60-3d438ae0a60d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsResolveRequiredAttributes
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
req.alt-api: KsResolveRequiredAttributes
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

# KsResolveRequiredAttributes function



## -description
The <b>KsResolveRequiredAttributes</b> function searches the attributes list that is attached to a data range for specified attributes and ensures that all specified attributes were found. 



## -syntax

````
HRESULT KsResolveRequiredAttributes(
  _In_     PKSDATARANGE     DataRange,
  _In_opt_ PKSMULTIPLE_ITEM Attributes
);
````


## -parameters

### -param DataRange [in]

Pointer to a <a href="stream.ksdatarange">KSDATARANGE</a> structure that possibly has an attached attribute list. <b>KsResolveRequiredAttributes</b> searches the data range's attribute list for the attributes at <i>Attributes</i>. An attribute list attached to a data range follows that data range.


### -param Attributes [in, optional]

Pointer to a buffer that contains a <a href="stream.ksmultiple_item">KSMULTIPLE_ITEM</a> structure, followed by a sequence of KSATTRIBUTE structures that describe attributes. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header. If this pointer is <b>NULL</b>, then <b>KsResolveRequiredAttributes</b> only succeeds if <i>DataRange</i> does not have an attached attribute list.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks


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
<a href="stream.ksattribute">KSATTRIBUTE</a>
</dt>
<dt>
<a href="stream.ksdatarange">KSDATARANGE</a>
</dt>
<dt>
<a href="stream.ksmultiple_item">KSMULTIPLE_ITEM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsResolveRequiredAttributes function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

