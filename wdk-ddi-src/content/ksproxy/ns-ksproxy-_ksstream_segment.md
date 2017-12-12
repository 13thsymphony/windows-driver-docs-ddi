---
UID: NS.KSPROXY._KSSTREAM_SEGMENT
title: _KSSTREAM_SEGMENT
author: windows-driver-content
description: The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.
old-location: stream\ksstream_segment.htm
old-project: stream
ms.assetid: 433b1346-f0f1-46f7-a1d8-e6397b2f7f05
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KSSTREAM_SEGMENT, *PKSSTREAM_SEGMENT, KSSTREAM_SEGMENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSSTREAM_SEGMENT
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

# _KSSTREAM_SEGMENT structure



## -description
The KSSTREAM_SEGMENT structure contains information that describes an I/O operation occurring on a stream.



## -syntax

````
typedef struct _KSSTREAM_SEGMENT {
  IKsInterfaceHandler *KsInterfaceHandler;
  IKsDataTypeHandler  *KsDataTypeHandler;
  KSIOOPERATION       IoOperation;
  HANDLE              CompletionEvent;
} KSSTREAM_SEGMENT, *PKSSTREAM_SEGMENT;
````


## -struct-fields

### -field KsInterfaceHandler

Pointer to a <a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a> interface for the I/O operation.


### -field KsDataTypeHandler

Pointer to a <a href="..\ksproxy\nn-ksproxy-iksdatatypehandler.md">IKsDataTypeHandler</a> interface for the I/O operation.


### -field IoOperation

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
 


### -field CompletionEvent

Handle to an event that is used to signal that the I/O operation completed.


## -remarks


## -requirements
<table>
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
<a href="..\ksproxy\nn-ksproxy-iksdatatypehandler.md">IKsDataTypeHandler</a>
</dt>
<dt>
<a href="..\ksproxy\nn-ksproxy-iksinterfacehandler.md">IKsInterfaceHandler</a>
</dt>
<dt>
<a href="stream.iksinterfacehandler_kscompleteio">IKsInterfaceHandler::KsCompleteIo</a>
</dt>
<dt>
<a href="stream.iksinterfacehandler_ksprocessmediasamples">IKsInterfaceHandler::KsProcessMediaSamples</a>
</dt>
<dt>
<a href="stream.ikspin_ksmediasamplescompleted">IKsPin::KsMediaSamplesCompleted</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSSTREAM_SEGMENT structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

