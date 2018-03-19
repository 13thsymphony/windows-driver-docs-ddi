---
UID: NF:ksproxy.IKsDataTypeHandler.KsIsMediaTypeInRanges
title: IKsDataTypeHandler::KsIsMediaTypeInRanges method
author: windows-driver-content
description: The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges.
old-location: stream\iksdatatypehandler_ksismediatypeinranges.htm
old-project: stream
ms.assetid: 354dcd2b-fa63-4574-94d8-149e3f199751
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler interface [Streaming Media Devices], KsIsMediaTypeInRanges method, IKsDataTypeHandler::KsIsMediaTypeInRanges, KsIsMediaTypeInRanges method [Streaming Media Devices], KsIsMediaTypeInRanges method [Streaming Media Devices], IKsDataTypeHandler interface, KsIsMediaTypeInRanges,IKsDataTypeHandler.KsIsMediaTypeInRanges, ksproxy/IKsDataTypeHandler::KsIsMediaTypeInRanges, ksproxy_ebd4f24e-02a2-4228-b11b-890693ece498.xml, stream.iksdatatypehandler_ksismediatypeinranges
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsDataTypeHandler.KsIsMediaTypeInRanges
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsIsMediaTypeInRanges method
The <b>KsIsMediaTypeInRanges</b> method validates that a media type is within the provided data ranges.

## Syntax

````
HRESULT KsIsMediaTypeInRanges(
  [in] PVOID DataRanges
);
````

## Parameters

`DataRanges`

Pointer to a buffer that contains a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure, followed by a sequence of extensible <a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a> structures, aligned on 64-bit boundaries. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

A client first calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559844">IKsDataTypeHandler::KsSetMediaType</a> method to assign a media type that the client references in subsequent operations on the data type handler. The client then calls <b>KsIsMediaTypeInRanges</b> to validate that the media type is within particular data ranges.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h |

## See Also

<a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559844">IKsDataTypeHandler::KsSetMediaType</a>