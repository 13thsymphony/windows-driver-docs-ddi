---
UID : NF:ksproxy.IKsDataTypeCompletion.KsCompleteMediaType
title : IKsDataTypeCompletion::KsCompleteMediaType method
author : windows-driver-content
description : The KsCompleteMediaType method completes a partially-specified media type that was first presented to the IAMStreamConfig::SetFormat method.
old-location : stream\iksdatatypecompletion_kscompletemediatype.htm
old-project : stream
ms.assetid : 0a6157cf-09ae-4640-9c54-3e9b91fd93a9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IKsDataTypeCompletion, IKsDataTypeCompletion::KsCompleteMediaType, KsCompleteMediaType
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IKsDataTypeCompletion.KsCompleteMediaType
req.alt-loc : ksproxy.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : PIPE_STATE
---


# KsCompleteMediaType method
The <b>KsCompleteMediaType</b> method completes a partially-specified media type that was first presented to the <b>IAMStreamConfig::SetFormat</b> method.

## Syntax

````
HRESULT KsCompleteMediaType(
  [in]      HANDLE        FilterHandle,
  [in]      ULONG         PinFactoryId,
  [in, out] AM_MEDIA_TYPE *AmMediaType
);
````

## Parameters

`FilterHandle`

Handle to the underlying KS filter.

`PinFactoryId`

Identifier of the pin factory against which the media type is being completed.

`AmMediaType`

Pointer to a AM_MEDIA_TYPE structure that describes the format of the media samples. <b>KsCompleteMediaType</b> receives partially specified media samples, completes the specification, and returns.


## Return Value

Returns NOERROR if successful and the media type was completed; otherwise, returns an error code.

## Remarks

The <b>KsCompleteMediaType</b> method is primarily used for video media types, in which the <b>biSizeImage</b> member of the <a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a> structure is known only to the driver, because of the private compression formats supported. If required, the data type handler can query the underlying KS filter in order to complete the given media type. 

When the proxy creates an instance of the data type handler for purposes of completing a media type, the proxy passes the media type to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559844">IKsDataTypeHandler::KsSetMediaType</a> method to first initialize this data type handler to the particular media type. 

For more information about <b>IAMStreamConfig::SetFormat</b> and AM_MEDIA_TYPE, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559844">IKsDataTypeHandler::KsSetMediaType</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_bitmapinfoheader.md">KS_BITMAPINFOHEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeCompletion::KsCompleteMediaType method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>