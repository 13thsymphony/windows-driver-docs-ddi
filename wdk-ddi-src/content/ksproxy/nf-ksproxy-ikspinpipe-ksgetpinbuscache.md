---
UID : NF:ksproxy.IKsPinPipe.KsGetPinBusCache
title : IKsPinPipe::KsGetPinBusCache method
author : windows-driver-content
description : Not recommended for application use.
old-location : stream\ikspinpipe_ksgetpinbuscache.htm
old-project : stream
ms.assetid : 4F38C7D7-E350-4FCB-A89B-CA87BA638AD3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsGetPinBusCache, KsGetPinBusCache method [Streaming Media Devices], IKsPinPipe interface, KsGetPinBusCache method [Streaming Media Devices], ksproxy/IKsPinPipe::KsGetPinBusCache, IKsPinPipe, IKsPinPipe interface [Streaming Media Devices], KsGetPinBusCache method, stream.ikspinpipe_ksgetpinbuscache, IKsPinPipe::KsGetPinBusCache
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : Windows
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


# KsGetPinBusCache method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Not recommended for application use.

## Syntax

````
HRESULT KsGetPinBusCache(
    
);
````

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ksproxy\nn-ksproxy-ikspinpipe.md">IKsPinPipe</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPinPipe::KsGetPinBusCache method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>