---
UID: NS:ndkpi._NDK_MR_DISPATCH
title: "_NDK_MR_DISPATCH"
author: windows-driver-content
description: The NDK_MR_DISPATCH structure specifies dispatch function entry points for the NDK memory region (MR) object.
old-location: netvista\ndk_mr_dispatch.htm
old-project: netvista
ms.assetid: C0EC5488-B08D-40A6-9E90-48E59B45B116
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_MR_DISPATCH, NDK_MR_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_MR_DISPATCH, PNDK_MR_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_MR_DISPATCH, ndkpi/NDK_MR_DISPATCH, ndkpi/PNDK_MR_DISPATCH, netvista.ndk_mr_dispatch
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
-	NDK_MR_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: NDK_MR_DISPATCH
---

# _NDK_MR_DISPATCH structure
The <b>NDK_MR_DISPATCH</b> structure specifies dispatch function entry points for the NDK memory region (MR) object.

## Syntax
```
typedef struct _NDK_MR_DISPATCH {
  NDK_FN_CLOSE_OBJECT                NdkCloseMr;
  NDK_FN_QUERY_EXTENSION_INTERFACE   NdkQueryExtension;
  NDK_FN_REGISTER_MR                 NdkRegisterMr;
  NDK_FN_DEREGISTER_MR               NdkDeregisterMr;
  NDK_FN_INITIALIZE_FAST_REGISTER_MR NdkInitializeFastRegisterMr;
  NDK_FN_GET_REMOTE_TOKEN_FROM_MR    NdkGetRemoteTokenFromMr;
  NDK_FN_GET_LOCAL_TOKEN_FROM_MR     NdkGetLocalTokenFromMr;
} NDK_MR_DISPATCH;
```

## Members


`NdkCloseMr`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a> dispatch function.

`NdkQueryExtension`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

`NdkRegisterMr`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439908">NDK_FN_REGISTER_MR</a> dispatch function.

`NdkDeregisterMr`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439884">NDK_FN_DEREGISTER_MR</a> dispatch function.

`NdkInitializeFastRegisterMr`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439900">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a> dispatch function.

`NdkGetRemoteTokenFromMr`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439897">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a> dispatch function.

`NdkGetLocalTokenFromMr`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439894">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a> dispatch function.

## Remarks
The <b>NDK_MR_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439884">NDK_FN_DEREGISTER_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439894">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439897">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439900">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439908">NDK_FN_REGISTER_MR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439922">NDK_MR</a>