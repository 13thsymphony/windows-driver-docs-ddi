---
UID: NF.ksproxy.IKsDataTypeHandler.KsIsMediaTypeInRanges
title: IKsDataTypeHandler::KsIsMediaTypeInRanges method
author: windows-driver-content
description: The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges.
old-location: stream\iksdatatypehandler_ksismediatypeinranges.htm
old-project: stream
ms.assetid: 354dcd2b-fa63-4574-94d8-149e3f199751
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler::KsIsMediaTypeInRanges, KsIsMediaTypeInRanges
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsDataTypeHandler.KsIsMediaTypeInRanges
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
---

# IKsDataTypeHandler::KsIsMediaTypeInRanges method



## -description
The <b>KsIsMediaTypeInRanges</b> method validates that a media type is within the provided data ranges.



## -syntax

````
HRESULT KsIsMediaTypeInRanges(
  [in] PVOID DataRanges
);
````


## -parameters

### -param DataRanges [in]

Pointer to a buffer that contains a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure, followed by a sequence of extensible <a href="stream.ksdatarange">KSDATARANGE</a> structures, aligned on 64-bit boundaries. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## -returns
Returns NOERROR if successful; otherwise, returns an error code.


## -remarks
A client first calls the <a href="stream.iksdatatypehandler_kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a> method to assign a media type that the client references in subsequent operations on the data type handler. The client then calls <b>KsIsMediaTypeInRanges</b> to validate that the media type is within particular data ranges. 


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
<dt>Ksproxy.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.iksdatatypehandler_kssetmediatype">IKsDataTypeHandler::KsSetMediaType</a>
</dt>
<dt>
<a href="stream.ksdatarange">KSDATARANGE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler::KsIsMediaTypeInRanges method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

