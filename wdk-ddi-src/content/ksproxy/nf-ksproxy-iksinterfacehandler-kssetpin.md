---
UID : NF:ksproxy.IKsInterfaceHandler.KsSetPin
title : IKsInterfaceHandler::KsSetPin method
author : windows-driver-content
description : The KsSetPin method informs the streaming interface handler about the pin with which to communicate when passing data.
old-location : stream\iksinterfacehandler_kssetpin.htm
old-project : stream
ms.assetid : 71e4be0a-a5a6-469a-948b-bc5277bc8cbe
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksproxy/IKsInterfaceHandler::KsSetPin, ksproxy_3746aba4-11e3-45a5-8495-eda1cad5bf9b.xml, KsSetPin method [Streaming Media Devices], KsSetPin, IKsInterfaceHandler interface [Streaming Media Devices], KsSetPin method, IKsInterfaceHandler, stream.iksinterfacehandler_kssetpin, KsSetPin method [Streaming Media Devices], IKsInterfaceHandler interface, IKsInterfaceHandler::KsSetPin
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ksproxy.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PIPE_STATE
---


# KsSetPin method
The <b>KsSetPin</b> method informs the streaming interface handler about the pin with which to communicate when passing data.

## Syntax

````
HRESULT KsSetPin(
  [in] IKsPin *KsPin
);
````

## Parameters

`KsPin`

Pointer to the <a href="..\ksproxy\nn-ksproxy-ikspin.md">IKsPin</a> interface for the pin to which this streaming interface handler is to be attached. This pin must support the <a href="..\ksproxy\nn-ksproxy-iksobject.md">IKsObject</a> interface from which the underlying kernel handle can be obtained.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The <b>KsSetPin</b> method is called after an instance of the interface handler is created but before any streaming is required of the instance.

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

<a href="..\ksproxy\nn-ksproxy-ikspin.md">IKsPin</a>

<a href="..\ksproxy\nn-ksproxy-iksobject.md">IKsObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsInterfaceHandler::KsSetPin method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>