---
UID: NS:ndkpi._NDK_MW_DISPATCH
title: "_NDK_MW_DISPATCH"
author: windows-driver-content
description: The NDK_MW_DISPATCH structure specifies dispatch function entry points for the NDK memory window (MW) object.
old-location: netvista\ndk_mw_dispatch.htm
old-project: netvista
ms.assetid: B35BDBBC-C8AB-4837-8637-30BA2E31831C
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NDK_MW_DISPATCH, NDK_MW_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_MW_DISPATCH, PNDK_MW_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_MW_DISPATCH, ndkpi/NDK_MW_DISPATCH, ndkpi/PNDK_MW_DISPATCH, netvista.ndk_mw_dispatch
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
-	NDK_MW_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_MW_DISPATCH
---

# _NDK_MW_DISPATCH structure
The <b>NDK_MW_DISPATCH</b> structure specifies dispatch function entry points for the NDK memory window (MW) object.

## Syntax
````
typedef struct _NDK_MW_DISPATCH {
  NDK_FN_CLOSE_OBJECT              NdkCloseMw;
  NDK_FN_QUERY_EXTENSION_INTERFACE NdkQueryExtension;
  NDK_FN_GET_REMOTE_TOKEN_FROM_MW  NdkGetRemoteTokenFromMw;
} NDK_MW_DISPATCH, *PNDK_MW_DISPATCH;
````

## Members


`NdkCloseMw`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.

`NdkQueryExtension`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

`NdkGetRemoteTokenFromMw`

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_remote_token_from_mw.md">NDK_FN_GET_REMOTE_TOKEN_FROM_MW</a> dispatch function.

## Remarks
The <b>NDK_MW_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_mw.md">NDK_MW</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_remote_token_from_mw.md">NDK_FN_GET_REMOTE_TOKEN_FROM_MW</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>