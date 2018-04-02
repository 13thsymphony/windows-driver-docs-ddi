---
UID: NS:ndkpi._NDK_CQ_DISPATCH
title: "_NDK_CQ_DISPATCH"
author: windows-driver-content
description: The NDK_CQ_DISPATCH structure specifies dispatch function entry points for the NDK completion queue (CQ) object.
old-location: netvista\ndk_cq_dispatch.htm
old-project: netvista
ms.assetid: 632E4FE8-BA03-4232-80E1-5EB3CC760D14
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_CQ_DISPATCH, NDK_CQ_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDK_CQ_DISPATCH, PNDK_CQ_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDK_CQ_DISPATCH, ndkpi/NDK_CQ_DISPATCH, ndkpi/PNDK_CQ_DISPATCH, netvista.ndk_cq_dispatch
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
-	NDK_CQ_DISPATCH
product: Windows
targetos: Windows
req.typenames: NDK_CQ_DISPATCH
---

# _NDK_CQ_DISPATCH structure
The <b>NDK_CQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK completion queue (CQ) object.

## Syntax
```
typedef struct _NDK_CQ_DISPATCH {
  NDK_FN_CLOSE_OBJECT                    NdkCloseCq;
  NDK_FN_QUERY_EXTENSION_INTERFACE       NdkQueryExtension;
  NDK_FN_RESIZE_CQ                       NdkResizeCq;
  NDK_FN_ARM_CQ                          NdkArmCq;
  NDK_FN_GET_CQ_RESULTS                  NdkGetCqResults;
  NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION NdkControlCqInterruptModeration;
  NDK_FN_GET_CQ_RESULTS_EX               NdkGetCqResultsEx;
} NDK_CQ_DISPATCH;
```

## Members


`NdkCloseCq`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a> dispatch function.

`NdkQueryExtension`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

`NdkResizeCq`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439913">NDK_FN_RESIZE_CQ</a> dispatch function.

`NdkArmCq`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439858">NDK_FN_ARM_CQ</a> dispatch function.

`NdkGetCqResults`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439891">NDK_FN_GET_CQ_RESULTS</a> dispatch function.

`NdkControlCqInterruptModeration`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/jj552973">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a> dispatch function.

`NdkGetCqResultsEx`

The entry point for the object's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265506">NDK_FN_GET_CQ_RESULTS_EX</a> dispatch function. 

<b>Note</b>  This member is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

## Remarks
The <b>NDK_CQ_DISPATCH</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439854">NDK_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439858">NDK_FN_ARM_CQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439863">NDK_FN_CLOSE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj552973">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439891">NDK_FN_GET_CQ_RESULTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439905">NDK_FN_QUERY_EXTENSION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439913">NDK_FN_RESIZE_CQ</a>