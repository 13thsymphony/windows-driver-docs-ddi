---
UID: NC.ndkpi.NDK_FN_CREATE_QP
title: NDK_FN_CREATE_QP
author: windows-driver-content
description: The NdkCreateQp (NDK_FN_CREATE_QP) function creates an NDK queue pair (QP) object.
old-location: netvista\ndk_fn_create_qp.htm
old-project: netvista
ms.assetid: 8B601E53-9BE9-4D84-819E-3B0BD07560BC
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkCreateQp
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# NDK_FN_CREATE_QP callback



## -description
The <i>NdkCreateQp</i> (<i>NDK_FN_CREATE_QP</i>) function creates an NDK queue pair (QP) object.



## -prototype

````
NDK_FN_CREATE_QP NdkCreateQp;

NTSTATUS NdkCreateQp(
  _In_     NDK_PD                   *pNdkPd,
  _In_     NDK_CQ                   *pReceiveCq,
  _In_     NDK_CQ                   *pInitiatorCq,
  _In_opt_ PVOID                    QPContext,
  _In_     ULONG                    ReceiveQueueDepth,
  _In_     ULONG                    InitiatorQueueDepth,
  _In_     ULONG                    MaxReceiveRequestSge,
  _In_     ULONG                    MaxInitiatorRequestSge,
  _In_     ULONG                    InlineDataSize,
  _In_     NDK_FN_CREATE_COMPLETION CreateCompletion,
  _In_opt_ PVOID                    RequestContext,
           _Outptr_ NDK_QP          **ppNdkQp
)
{ ... }
````


## -parameters

### -param pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="netvista.ndk_pd">NDK_PD</a>).


### -param pReceiveCq [in]

A pointer to a completion queue (CQ) to use for receive request completions (<a href="netvista.ndk_cq">NDK_CQ</a>).


### -param pInitiatorCq [in]

A pointer to a CQ to use for initiator request completions.


### -param QPContext [in, optional]

A context value to be returned in the <b>QPContext</b> member of the  <a href="netvista.ndk_result">NDK_RESULT</a> structure for all requests that are posted over this QP.


### -param ReceiveQueueDepth [in]

The maximum number of receive requests that can be outstanding over the QP. This value must be less than or equal to the value in the  <b>MaxReceiveQueueDepth</b> member of the  <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.


### -param InitiatorQueueDepth [in]

The maximum number of initiator requests that can be outstanding over the QP. This value must be less than or equal to the value in the  <b>MaxInitiatorQueueDepth</b> member of the  NDK_ADAPTER_INFO structure.


### -param MaxReceiveRequestSge [in]

The maximum number of SGEs that can be supported in a single receive request. This value must be less than or equal to the value in the  <b>MaxReceiveRequestSge</b> member of the  NDK_ADAPTER_INFO structure.


### -param MaxInitiatorRequestSge [in]

The maximum number of SGEs that can be supported in a single initiator request. This value must be less than or equal to the value in the  <b>MaxInitiatorRequestSge</b> member of the  NDK_ADAPTER_INFO structure.


### -param InlineDataSize [in]

The maximum amount of inline data in bytes that can be sent in a single send or write request. This value must be less than or equal to the value in the  <b>MaxInlineDataSize</b> member of the  NDK_ADAPTER_INFO structure.


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


### -param ppNdkQp 

A pointer to a created QP object (<a href="netvista.ndk_qp">NDK_QP</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns
The 
     <i>NdkCreateQp</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The QP object was created successfully and returned with the <i>*ppNdkQp</i> parameter.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The request failed because the requested <i>ReceiveQueueDepth</i>, <i>InitiatorQueueDepth</i>,  <i>MaxReceiveRequestSge</i>, <i>MaxInitiatorRequestSge</i>, or <i>InlineDataSize</i> are not within the limits that are specified in the  <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The request failed due to insufficient resources. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
The <i>NdkCreateQp</i> function creates an   NDK queue pair (QP) object.  A QP consists of a receive queue and an initiator queue. The receive queue is used to  post receive requests. An initiator queue is used for initiating send, bind, fast-register, read, write, and invalidate requests.

If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkQp</i> parameter. If <i>NdkCreateQp</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a>
</dt>
<dt>
<a href="netvista.ndk_cq">NDK_CQ</a>
</dt>
<dt>
<a href="netvista.ndk_pd">NDK_PD</a>
</dt>
<dt>
<a href="netvista.ndk_qp">NDK_QP</a>
</dt>
<dt>
<a href="netvista.ndk_result">NDK_RESULT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_QP callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

