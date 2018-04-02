---
UID: NS:ndkpi._NDK_SRQ_DISPATCH
title: "_NDK_SRQ_DISPATCH"
author: windows-driver-content
description: The NDK_SRQ_DISPATCH structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq_dispatch.htm
old-project: netvista
ms.assetid: 13297898-A72B-4771-A022-FDCBC281CEA0
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_SRQ_DISPATCH, NDK_SRQ_DISPATCH structure [Network Drivers Starting with Windows Vista], _NDK_SRQ_DISPATCH, ndkpi/NDK_SRQ_DISPATCH, netvista.ndk_srq_dispatch
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_SRQ_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# _NDK_SRQ_DISPATCH structure
The <b>NDK_SRQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.

## Syntax
```
typedef struct _NDK_SRQ_DISPATCH {
  NDK_FN_CLOSE_OBJECT              NdkCloseSrq;
  NDK_FN_QUERY_EXTENSION_INTERFACE NdkQueryExtension;
  NDK_FN_MODIFY_SRQ                NdkModifySrq;
  NDK_FN_SRQ_RECEIVE               NdkSrqReceive;
} NDK_SRQ_DISPATCH;
```

## Members


`NdkCloseSrq`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a> dispatch function.

`NdkQueryExtension`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

`NdkModifySrq`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439903">NDK_FN_MODIFY_SRQ</a> dispatch function.

`NdkSrqReceive`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439916">NDK_FN_SRQ_RECEIVE</a> dispatch function.

## Remarks
The <b>NDK_SRQ_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439903">NDK_FN_MODIFY_SRQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439916">NDK_FN_SRQ_RECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439939">NDK_SRQ</a>