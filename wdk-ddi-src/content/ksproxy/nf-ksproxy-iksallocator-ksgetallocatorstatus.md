---
UID: NF:ksproxy.IKsAllocator.KsGetAllocatorStatus
title: IKsAllocator::KsGetAllocatorStatus method
author: windows-driver-content
description: Retrieves the status of an allocator.
old-location: stream\iksallocator_ksgetallocatorstatus.htm
old-project: stream
ms.assetid: 139F4465-1228-4603-B92F-4CB73E1A6DC0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsAllocator, IKsAllocator interface [Streaming Media Devices], KsGetAllocatorStatus method, IKsAllocator::KsGetAllocatorStatus, KsGetAllocatorStatus method [Streaming Media Devices], KsGetAllocatorStatus method [Streaming Media Devices], IKsAllocator interface, KsGetAllocatorStatus,IKsAllocator.KsGetAllocatorStatus, ksproxy/IKsAllocator::KsGetAllocatorStatus, stream.iksallocator_ksgetallocatorstatus
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
-	IKsAllocator.KsGetAllocatorStatus
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsAllocator::KsGetAllocatorStatus method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Retrieves the status of an allocator.

## Syntax

```
HRESULT KsGetAllocatorStatus(
  PKSSTREAMALLOCATOR_STATUS AllocatorStatus
);
```

## Parameters

`AllocatorStatus`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559719">IKsAllocator</a>