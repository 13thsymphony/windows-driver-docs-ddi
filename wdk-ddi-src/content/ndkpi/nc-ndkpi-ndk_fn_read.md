---
UID: NC:ndkpi.NDK_FN_READ
title: NDK_FN_READ
author: windows-driver-content
description: The NdkRead (NDK_FN_READ) function posts a read request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_read.htm
old-project: netvista
ms.assetid: A6D2C017-0D50-4AD7-9241-110C97F5FE92
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_read, NdkRead callback function [Network Drivers Starting with Windows Vista], NdkRead, NDK_FN_READ, NDK_FN_READ, ndkpi/NdkRead, NDK_OP_FLAG_SILENT_SUCCESS, NDK_OP_FLAG_READ_FENCE, NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE, NDK_OP_FLAG_DEFER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkRead
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---


# NDK_FN_READ callback function
The <i>NdkRead</i> (<i>NDK_FN_READ</i>) function posts a read request on an NDK queue pair (QP).

## Syntax

```
NDK_FN_READ NdkFnRead;

NTSTATUS NdkFnRead(
  NDK_QP *pNdkQp,
  PVOID RequestContext,
  CONST NDK_SGE,
  ULONG nSge,
  UINT64 RemoteAddress,
  UINT32 RemoteToken,
  ULONG Flags
)
{...}
```

## Parameters

`*pNdkQp`

A pointer to an NDK queue pair (QP) object (<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>).

`RequestContext`

A context value to be returned in the <b>RequestContext</b> member of the <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structure for this request.

`NDK_SGE`



`nSge`

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.

`RemoteAddress`

A remote address to read from that is presented in the local host's byte order. The NDK consumer can   add  an offset  to the remotely-provided value.

`RemoteToken`

A remotely-provided memory token that  is an opaque array of bytes from the NDK consumer.

`Flags`

A bitwise OR of flags which specifies the operations that are allowed. The following flags are supported:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_SILENT_SUCCESS"></a><a id="ndk_op_flag_silent_success"></a><dl>
<dt><b>NDK_OP_FLAG_SILENT_SUCCESS</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Indicates the successful completion of this request does not generate a completion event in the outbound completion queue. However, requests that fail do generate an event in the completion queue.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_READ_FENCE"></a><a id="ndk_op_flag_read_fence"></a><dl>
<dt><b>NDK_OP_FLAG_READ_FENCE</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Indicates that all prior read requests must be complete before the hardware begins processing this request.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE"></a><a id="ndk_op_flag_rdma_read_local_invalidate"></a><dl>
<dt><b>NDK_OP_FLAG_RDMA_READ_LOCAL_INVALIDATE</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
If this flag is set and the provider also reports <b>NDK_ADAPTER_FLAG_RDMA_READ_LOCAL_INVALIDATE_SUPPORTED</b> adapter capability in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure, successful completion of the <i>NdkRead</i> function means that the first buffer specified in the <i>pSgl</i> parameter is invalidated. Unsuccessful completion leaves the buffer and token in an undefined state. This flag is ignored if the provider does not report <b>NDK_ADAPTER_FLAG_RDMA_READ_LOCAL_INVALIDATE_SUPPORTED</b> adapter capability in the <b>NDK_ADAPTER_INFO</b> structure.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
<tr>
<td width="40%"><a id="NDK_OP_FLAG_DEFER"></a><a id="ndk_op_flag_defer"></a><dl>
<dt><b>NDK_OP_FLAG_DEFER</b></dt>
<dt>0x00000200</dt>
</dl>
</td>
<td width="60%">
Indicates to the NDK provider that it may defer indicating the request to hardware for processing. For more information about this flag, see <a href="https://msdn.microsoft.com/DA2D0FCA-D84B-4599-A560-8F87A0918D99">NDKPI Deferred Processing Scheme</a>.

<b>Note</b>  This flag is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.

</td>
</tr>
</table>


## Return Value

The 
     <i>NdkRead</i> function returns one of the following NTSTATUS codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was posted successfully. A completion entry will be queued to the CQ when the work request is completed.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The QP is not connected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REMOTE_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
	The request tried to read beyond the size of the remote memory.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>

## Remarks

<i>NdkRead</i> posts a read request on a queue pair (QP).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Target Platform** | Windows |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ndkpi\ns-ndkpi-_ndk_sge.md">NDK_SGE</a>

<a href="https://msdn.microsoft.com/2BF6F253-FCB4-4A61-9A67-81092F3C44E4">NDKPI Work Request Posting Requirements</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>

<a href="https://msdn.microsoft.com/DA2D0FCA-D84B-4599-A560-8F87A0918D99">NDKPI Deferred Processing Scheme</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_arm_cq.md">NDK_FN_ARM_CQ</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_READ callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>