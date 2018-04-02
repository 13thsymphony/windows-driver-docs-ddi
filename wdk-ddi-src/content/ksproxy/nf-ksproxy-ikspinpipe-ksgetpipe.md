---
UID: NF:ksproxy.IKsPinPipe.KsGetPipe
title: IKsPinPipe::KsGetPipe method
author: windows-driver-content
description: Not recommended for application use.
old-location: stream\ikspinpipe_ksgetpipe.htm
old-project: stream
ms.assetid: 5672C7E2-83AA-4BDC-BE60-E2BC54BD636F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPinPipe, IKsPinPipe interface [Streaming Media Devices], KsGetPipe method, IKsPinPipe::KsGetPipe, KsGetPipe method [Streaming Media Devices], KsGetPipe method [Streaming Media Devices], IKsPinPipe interface, KsGetPipe,IKsPinPipe.KsGetPipe, ksproxy/IKsPinPipe::KsGetPipe, stream.ikspinpipe_ksgetpipe
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
-	IKsPinPipe.KsGetPipe
product:
- Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsPinPipe::KsGetPipe method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Not recommended for application use.

## Syntax

```
IKsAllocatorEx * KsGetPipe(
  KSPEEKOPERATION Operation
);
```

## Parameters

`Operation`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559922">IKsPinPipe</a>