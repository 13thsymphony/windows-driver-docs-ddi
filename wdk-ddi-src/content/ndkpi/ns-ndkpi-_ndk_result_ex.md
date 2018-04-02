---
UID: NS:ndkpi._NDK_RESULT_EX
title: "_NDK_RESULT_EX"
author: windows-driver-content
description: The NDK_RESULT_EX structure returns the results for an NDK request operation. It is identical to the NDK_RESULT structure, except that it has additional Type and TypeSpecificCompletionOutput members.
old-location: netvista\ndk_result_ex.htm
old-project: netvista
ms.assetid: C79BF9FC-4836-48AD-8E9F-41278BB01E11
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDK_RESULT_EX, NDK_RESULT_EX structure [Network Drivers Starting with Windows Vista], PNDK_RESULT_EX, PNDK_RESULT_EX structure pointer [Network Drivers Starting with Windows Vista], _NDK_RESULT_EX, ndkpi/NDK_RESULT_EX, ndkpi/PNDK_RESULT_EX, netvista.ndk_result_ex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.40 and later.
req.target-min-winversvr: Windows Server 2012 R2
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
-	NDK_RESULT_EX
product: Windows
targetos: Windows
req.typenames: NDK_RESULT_EX
---

# _NDK_RESULT_EX structure
The <b>NDK_RESULT_EX</b> structure returns the results for an NDK request operation. It is identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a> structure, except that it has additional <b>Type</b> and <b>TypeSpecificCompletionOutput</b> members.

## Syntax
```
typedef struct _NDK_RESULT_EX {
  NTSTATUS           Status;
  ULONG              BytesTransferred;
  PVOID              QPContext;
  PVOID              RequestContext;
  NDK_OPERATION_TYPE Type;
  ULONG_PTR          TypeSpecificCompletionOutput;
} NDK_RESULT_EX;
```

## Members


`Status`

The NDK request completion status.

`BytesTransferred`

The number of bytes transferred. The value of this member  is valid only for <i>NdkReceive</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a>) request completions. The member is undefined for all other NDK request completions.

`QPContext`

A context value for all requests that are posted over a queue pair (QP). The NDK consumer specified this  pointer when it called the <i>NdkCreateQp</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439878">NDK_FN_CREATE_QP</a>) function to create the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a> object.

`RequestContext`

A request context value specified by the NDK consumer when  a request is posted.

`Type`

An <a href="https://msdn.microsoft.com/library/windows/hardware/dn265508">NDK_OPERATION_TYPE</a> enumeration value that specifies the type of operation that is being completed.

`TypeSpecificCompletionOutput`

The type-specific completion output, if any. If the  <b>Type</b> member is <b>NdkOperationTypeReceiveAndInvalidate</b>, this member is a 32-bit field, which contains the token to be invalidated before signaling this completion. Otherwise, this member is undefined.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.40 and later. None supported,Supported in NDIS 6.40 and later. |
| **Header** | ndkpi.h (include Ndkpi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439878">NDK_FN_CREATE_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265508">NDK_OPERATION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439933">NDK_QP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439935">NDK_RESULT</a>