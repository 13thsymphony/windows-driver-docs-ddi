---
UID: NS:ndkpi._NDK_MR_DISPATCH
title: "_NDK_MR_DISPATCH"
author: windows-driver-content
description: The NDK_MR_DISPATCH structure specifies dispatch function entry points for the NDK memory region (MR) object.
old-location: netvista\ndk_mr_dispatch.htm
old-project: netvista
ms.assetid: C0EC5488-B08D-40A6-9E90-48E59B45B116
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndkpi/NDK_MR_DISPATCH, ndkpi/PNDK_MR_DISPATCH, NDK_MR_DISPATCH structure [Network Drivers Starting with Windows Vista], netvista.ndk_mr_dispatch, _NDK_MR_DISPATCH, PNDK_MR_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], NDK_MR_DISPATCH, PNDK_MR_DISPATCH
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndkpi.h
apiname:
-	NDK_MR_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_MR_DISPATCH
---

# _NDK_MR_DISPATCH structure
The <b>NDK_MR_DISPATCH</b> structure specifies dispatch function entry points for the NDK memory region (MR) object.

## Syntax
````
typedef struct _NDK_MR_DISPATCH {
  NDK_FN_CLOSE_OBJECT                NdkCloseMr;
  NDK_FN_QUERY_EXTENSION_INTERFACE   NdkQueryExtension;
  NDK_FN_REGISTER_MR                 NdkRegisterMr;
  NDK_FN_DEREGISTER_MR               NdkDeregisterMr;
  NDK_FN_INITIALIZE_FAST_REGISTER_MR NdkInitializeFastRegisterMr;
  NDK_FN_GET_REMOTE_TOKEN_FROM_MR    NdkGetRemoteTokenFromMr;
  NDK_FN_GET_LOCAL_TOKEN_FROM_MR     NdkGetLocalTokenFromMr;
} NDK_MR_DISPATCH, *PNDK_MR_DISPATCH;
````

## Members


`NdkCloseMr`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.

`NdkDeregisterMr`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a> dispatch function.

`NdkGetLocalTokenFromMr`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_local_token_from_mr.md">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a> dispatch function.

`NdkGetRemoteTokenFromMr`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_remote_token_from_mr.md">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a> dispatch function.

`NdkInitializeFastRegisterMr`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_initialize_fast_register_mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a> dispatch function.

`NdkQueryExtension`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

`NdkRegisterMr`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_register_mr.md">NDK_FN_REGISTER_MR</a> dispatch function.

## Remarks
The <b>NDK_MR_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_initialize_fast_register_mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_register_mr.md">NDK_FN_REGISTER_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_remote_token_from_mr.md">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_local_token_from_mr.md">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_MR_DISPATCH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>