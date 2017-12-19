---
UID: NC.ndkpi.NDK_FN_RESIZE_CQ
title: NDK_FN_RESIZE_CQ
author: windows-driver-content
description: The NdkResizeCq (NDK_FN_RESIZE_CQ) function changes the size of an NDK completion queue (CQ).
old-location: netvista\ndk_fn_resize_cq.htm
old-project: NetVista
ms.assetid: DFAEAA42-B1B5-43AA-A573-8434FAF3B446
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkResizeCq
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

# NDK_FN_RESIZE_CQ callback



## -description
The <i>NdkResizeCq</i> (<i>NDK_FN_RESIZE_CQ</i>) function changes the size of an NDK completion queue (CQ).



## -prototype

````
NDK_FN_RESIZE_CQ NdkResizeCq;

NTSTATUS NdkResizeCq(
  _In_     NDK_CQ                    *pNdkCq,
  _In_     ULONG                     CqDepth,
  _In_     NDK_FN_REQUEST_COMPLETION RequestCompletion,
  _In_opt_ PVOID                     RequestContext
)
{ ... }
````


## -parameters

### -param pNdkCq [in]


A pointer to an NDK completion queue (CQ) object (<a href="netvista.ndk_cq">NDK_CQ</a>).


### -param CqDepth [in]


The new number of completion entries that the CQ can hold. The CQ size must be  be less than or equal to the value that is specified in the <b>MaxCqDepth</b> member in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.


### -param RequestCompletion [in]

A pointer to an <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function.


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## -returns
The <i>NDK_FN_RESIZE_CQ</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The CQ was resized successfully.

<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The request failed because the CQ size that is specified in the <i>CqDepth</i> parameter is greater than the value in the  <b>MaxCqDepth</b> member in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The request failed due to insufficient resources. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
<i>NdkResizeCq</i>  changes the number of completion entries that a CQ can hold.


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
<a href="netvista.ndk_cq_dispatch">NDK_CQ_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_RESIZE_CQ callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

