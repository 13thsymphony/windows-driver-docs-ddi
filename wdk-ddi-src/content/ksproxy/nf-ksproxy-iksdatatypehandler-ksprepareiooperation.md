---
UID: NF.ksproxy.IKsDataTypeHandler.KsPrepareIoOperation
title: IKsDataTypeHandler::KsPrepareIoOperation method
author: windows-driver-content
description: The KsPrepareIoOperation method initializes the extended header and prepares the media sample for an I/O operation.
old-location: stream\iksdatatypehandler_ksprepareiooperation.htm
old-project: stream
ms.assetid: 16411d58-5fff-430f-b96d-78eed1dbb01c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKsDataTypeHandler, IKsDataTypeHandler::KsPrepareIoOperation, KsPrepareIoOperation
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
req.alt-api: IKsDataTypeHandler.KsPrepareIoOperation
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

# IKsDataTypeHandler::KsPrepareIoOperation method



## -description
The <b>KsPrepareIoOperation</b> method initializes the extended header and prepares the media sample for an I/O operation.



## -syntax

````
HRESULT KsPrepareIoOperation(
  [in, out] IMediaSample  *Sample,
  [in, out] PVOID         StreamHeader,
  [in]      KSIOOPERATION IoOperation
);
````


## -parameters

### -param Sample [in, out]

Pointer to the <b>IMediaSample</b> interface for the associated media sample.


### -param StreamHeader [in, out]

Pointer to a buffer that contains the extended header information.


### -param IoOperation [in]

Value that specifies the type of I/O operation. This value can be one of the following values from the KSIOOPERATION enumerated type:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsIoOperation_Write</b>

</td>
<td>
Write data to stream.

</td>
</tr>
<tr>
<td>
<b>KsIoOperation_Read</b>

</td>
<td>
Read data from stream.

</td>
</tr>
</table>
 


## -returns
Returns NOERROR if successful; otherwise, returns an error code. If the stream's major type is KSDATAFORMAT_TYPE_AUDIO, a <b>KsPrepareIoOperation</b> call is inapplicable, so <b>KsPrepareIoOperation</b> automatically returns NOERROR.


## -remarks
The client only calls <b>KsPrepareIoOperation</b> if the data type handler indicated to the client the existence of extended header information in a call to the <a href="stream.iksdatatypehandler_ksqueryextendedsize">IKsDataTypeHandler::KsQueryExtendedSize</a> method.

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.


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
<a href="stream.iksdatatypehandler_ksqueryextendedsize">IKsDataTypeHandler::KsQueryExtendedSize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler::KsPrepareIoOperation method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

