---
UID: NF:ksproxy.IKsPinPipe.KsSetPinBusCache
title: IKsPinPipe::KsSetPinBusCache method
author: windows-driver-content
description: Not recommended for application use.
old-location: stream\ikspinpipe_kssetpinbuscache.htm
old-project: stream
ms.assetid: 5340DB05-12D9-4965-B207-BA113F3801A7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPinPipe, IKsPinPipe interface [Streaming Media Devices], KsSetPinBusCache method, IKsPinPipe::KsSetPinBusCache, KsSetPinBusCache method [Streaming Media Devices], KsSetPinBusCache method [Streaming Media Devices], IKsPinPipe interface, KsSetPinBusCache,IKsPinPipe.KsSetPinBusCache, ksproxy/IKsPinPipe::KsSetPinBusCache, stream.ikspinpipe_kssetpinbuscache
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
-	IKsPinPipe.KsSetPinBusCache
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsPinPipe::KsSetPinBusCache method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Not recommended for application use.

## Syntax

```
HRESULT KsSetPinBusCache(
  GUID Bus
);
```

## Parameters

`Bus`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559922">IKsPinPipe</a>