---
UID: NN:ksproxy.IKsDataTypeHandler
title: IKsDataTypeHandler
author: windows-driver-content
description: The IKsDataTypeHandler interface provides methods that perform optional preprocessing and postprocessing of media samples.
old-location: stream\iksdatatypehandler.htm
old-project: stream
ms.assetid: ef08d375-1ac6-489f-9fd4-f791ce82c553
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.iksdatatypehandler, IKsDataTypeHandler interface [Streaming Media Devices], IKsDataTypeHandler interface [Streaming Media Devices], described, IKsDataTypeHandler, ksproxy/IKsDataTypeHandler, ksproxy_fd2ab182-1556-438e-bc5e-fe1339d0d865.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsDataTypeHandler
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsDataTypeHandler interface

The <b>IKsDataTypeHandler</b> interface provides methods that perform optional preprocessing and postprocessing of media samples. This interface also can return the size of extra stream header information that is required for processing and can determine if a particular media type is within a given set of kernel streaming data ranges. 

The IID for this interface is IID_IKsDataTypeHandler.

## Methods

<p>The <b>IKsDataTypeHandler</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [ksproxy.IKsDataTypeHandler.KsCompleteIoOperation](nf-ksproxy-iksdatatypehandler-kscompleteiooperation.md) | The KsCompleteIoOperation method cleans up the extended header and completes the input and output (I/O) operation. |
| [ksproxy.IKsDataTypeHandler.KsIsMediaTypeInRanges](nf-ksproxy-iksdatatypehandler-ksismediatypeinranges.md) | The KsIsMediaTypeInRanges method validates that a media type is within the provided data ranges. |
| [ksproxy.IKsDataTypeHandler.KsPrepareIoOperation](nf-ksproxy-iksdatatypehandler-ksprepareiooperation.md) | The KsPrepareIoOperation method initializes the extended header and prepares the media sample for an I/O operation. |
| [ksproxy.IKsDataTypeHandler.KsQueryExtendedSize](nf-ksproxy-iksdatatypehandler-ksqueryextendedsize.md) | The KsQueryExtendedSize method retrieves extended header information required for input and output (I/O) operations. |
| [ksproxy.IKsDataTypeHandler.KsSetMediaType](nf-ksproxy-iksdatatypehandler-kssetmediatype.md) | The KsSetMediaType method sets the media type for a data type handler. |

## Remarks

In order to keep the proxy data type neutral, optional data type handlers can be loaded to massage the data stream as it passes to or from kernel-mode filters. You should implement a data type handler as a COM server that, at least, supports the <b>IKsDataTypeHandler</b> interface. Your data type handler can optionally support the <a href="..\ksproxy\nn-ksproxy-iksdatatypecompletion.md">IKsDataTypeCompletion</a> interface. 

A data type handler is typically loaded during the pin connection process, and unloaded when the connection is broken. However, a data type handler is sometimes loaded briefly for other purposes. For instance, if an application uses DirectShow's <b>IAMStreamConfig::SetFormat</b> method, the application possibly uses a data type handler to complete a partial media type parameter sent to the method. 

The proxy uses the GUIDs from the media type as COM server classes to determine what if any data type handler to load. As long as the data type handler is registered as a COM server under an expected GUID class that the proxy looks for, the data type handler is loaded. The major format type is first used to attempt to open a data type handler COM server, followed by the subtype and format specifier if opening the data type handler fails using the major format type. If any of the attempts succeed, the proxy queries for the <b>IKsDataTypeHandler</b> interface and calls the interface's <b>KsSetMediaType</b> method to establish the current media type being used with the handler, in case the handler supports many types. If no handler is found, then the proxy assumes none is necessary when marshaling the stream to or from kernel mode, or to perform any other tasks necessary.

On a data type handler create request through <b>CoCreateInstance</b>, the server is always presented an outer <b>IUnknown</b> with which to create the COM object. This <b>IUnknown</b> is an interface on the pin object that is loading this handler. The <b>IUnknown</b> interface pointer may be used to query information or interfaces from the pin, such as the <b>IKsPin</b> or <b>IKsControl</b> interfaces, although the kernel-mode pin may not have been created at the time the handler is loaded. No reference should be left on the outer object through acquiring any interfaces, as it will result in a circular reference count. Using the interfaces without a reference count is acceptable, because the outer object owns the handler and, by definition, is destroyed when the outer object's reference count reaches zero.

For more information about <b>IAMStreamConfig::SetFormat</b> and <b>CoCreateInstance</b>, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h |

## See Also

<a href="..\ksproxy\nn-ksproxy-iksdatatypecompletion.md">IKsDataTypeCompletion</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsDataTypeHandler interface%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>