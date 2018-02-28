---
UID: NC:ndkpi.NDK_FN_CREATE_QP_WITH_SRQ
title: NDK_FN_CREATE_QP_WITH_SRQ
author: windows-driver-content
description: The NdkCreateQpWithSrq (NDK_FN_CREATE_QP_WITH_SRQ) function create an NDK queue pair (QP) object with an NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_fn_create_qp_with_srq.htm
old-project: netvista
ms.assetid: B3AAC8BE-E874-48C7-9DF6-0C9A6BDBB9B5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDK_FN_CREATE_QP_WITH_SRQ, NdkCreateQpWithSrq, NdkCreateQpWithSrq callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateQpWithSrq, netvista.ndk_fn_create_qp_with_srq
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndkpi.h
api_name:
-	NdkCreateQpWithSrq
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---


# NDK_FN_CREATE_QP_WITH_SRQ callback function
The <i>NdkCreateQpWithSrq</i> (<i>NDK_FN_CREATE_QP_WITH_SRQ</i>) function create an NDK queue pair (QP) object with an NDK shared receive queue (SRQ) object.

## Syntax

```
NDK_FN_CREATE_QP_WITH_SRQ NdkFnCreateQpWithSrq;

NTSTATUS NdkFnCreateQpWithSrq(
  NDK_PD *pNdkPd,
  NDK_CQ *pReceiveCq,
  NDK_CQ *pInitiatorCq,
  NDK_SRQ *pSrq,
  PVOID QPContext,
  ULONG InitiatorQueueDepth,
  ULONG MaxInitiatorRequestSge,
  ULONG InlineDataSize,
  NDK_FN_CREATE_COMPLETION CreateCompletion,
  PVOID RequestContext,
  NDK_QP **ppNdkQp
)
{...}
```

## Parameters

`*pNdkPd`

A pointer to an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>).

`*pReceiveCq`

A pointer to a completion queue (CQ) to use for receive request completions (<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>).

`*pInitiatorCq`

A pointer to a CQ to use for initiator request completions.

`*pSrq`

A pointer to an NDK shared receive queue (SRQ) object (<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>) to post receive requests.

`QPContext`

A context value to be returned in the <b>QPContext</b> member of the  <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structure for all requests that are posted over this QP.

`InitiatorQueueDepth`

The maximum number of initiator requests that can be outstanding over the QP. This value must be less than or equal to the value in the  <b>MaxInitiatorQueueDepth</b> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.

`MaxInitiatorRequestSge`

The maximum number of SGEs that can be supported in a single initiator request. This value must be less than or equal to the value in the  <b>MaxInitiatorRequestSge</b> member of the  NDK_ADAPTER_INFO structure.

`InlineDataSize`

The maximum amount of inline data in bytes that can be sent in a single send or write request. This value must be less than or equal to the value in the  <b>MaxInlineDataSize</b> member of the  NDK_ADAPTER_INFO structure.

`CreateCompletion`

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.

`RequestContext`

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.

`**ppNdkQp`




## Return Value

The 
     <i>NdkCreateQpWithSrq</i> function returns one of the following NTSTATUS codes.

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
The QP object was created successfully and returned with the <i>*ppNdkQp</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the requested <i>InitiatorQueueDepth</i>,  <i>MaxInitiatorRequestSge</i> or <i>InlineDataSize</i> is not within the limits that are specified in the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request failed due to insufficient resources. 

<div class="alert"><b>Important</b>  The request can fail inline as well as asynchronously with this status code.</div>
<div> </div>
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

The <i>NdkCreateQpWithSrq</i> function creates an   NDK queue pair (QP) object with a shared receive queue (SRQ).  A QP consists of a receive queue and an initiator queue. The receive queue is used to  post receive requests. An initiator queue is used for initiating send, bind, fast-register, read, write, and invalidate requests.

If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkQp</i> parameter. If <i>NdkCreateQpWithSrq</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ndkpi\ns-ndkpi-_ndk_srq.md">NDK_SRQ</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_QP_WITH_SRQ callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>