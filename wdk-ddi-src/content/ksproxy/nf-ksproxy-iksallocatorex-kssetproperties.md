---
UID: NF:ksproxy.IKsAllocatorEx.KsSetProperties
title: IKsAllocatorEx::KsSetProperties method
author: windows-driver-content
description: Sets the properties for an allocator.
old-location: stream\iksallocatorex_kssetproperties.htm
old-project: stream
ms.assetid: 17145801-5EE4-4022-997A-03B14C794D2F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsAllocatorEx, IKsAllocatorEx interface [Streaming Media Devices], KsSetProperties method, IKsAllocatorEx::KsSetProperties, KsSetProperties method [Streaming Media Devices], KsSetProperties method [Streaming Media Devices], IKsAllocatorEx interface, KsSetProperties,IKsAllocatorEx.KsSetProperties, ksproxy/IKsAllocatorEx::KsSetProperties, stream.iksallocatorex_kssetproperties
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
-	IKsAllocatorEx.KsSetProperties
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsAllocatorEx::KsSetProperties method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Sets the properties for an allocator.

## Syntax

```
void KsSetProperties(

);
```

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559724">IKsAllocatorEx</a>