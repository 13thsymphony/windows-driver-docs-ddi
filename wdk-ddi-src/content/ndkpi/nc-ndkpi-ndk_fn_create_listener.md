---
UID: NC:ndkpi.NDK_FN_CREATE_LISTENER
title: NDK_FN_CREATE_LISTENER
author: windows-driver-content
description: The NdkCreateListener (NDK_FN_CREATE_LISTENER) function creates an NDK listener object.
old-location: netvista\ndk_fn_create_listener.htm
old-project: netvista
ms.assetid: CC6259B8-AF3B-4FCE-94E3-7A5CD80C64A7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NDK_FN_CREATE_LISTENER, NdkCreateListener, NdkCreateListener callback function [Network Drivers Starting with Windows Vista], ndkpi/NdkCreateListener, netvista.ndk_fn_create_listener
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
-	NdkCreateListener
product: Windows
targetos: Windows
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---


# NDK_FN_CREATE_LISTENER callback function
The <i>NdkCreateListener</i> (<i>NDK_FN_CREATE_LISTENER</i>) function creates an NDK listener object.

## Syntax

```
NDK_FN_CREATE_LISTENER NdkFnCreateListener;

NTSTATUS NdkFnCreateListener(
  NDK_ADAPTER *pNdkAdapter,
  NDK_FN_CONNECT_EVENT_CALLBACK ConnectEvent,
  PVOID ConnectEventContext,
  NDK_FN_CREATE_COMPLETION CreateCompletion,
  PVOID RequestContext,
  NDK_LISTENER **ppNdkListener
)
{...}
```

## Parameters

`*pNdkAdapter`

A pointer to an NDK adapter object (<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>).

`ConnectEvent`

A pointer to the <i>NdkConnectEventCallback </i> function   (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>) that the provider uses to notify the consumer for each incoming connection request.

`ConnectEventContext`

A context value that the NDK provider passes back to the <i>NdkConnectEventCallback </i> function that is specified in the <i>ConnectEvent</i> parameter.

`CreateCompletion`

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.

`RequestContext`

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.

`**ppNdkListener`




## Return Value

The <i>NdkCreateListener</i> function returns one of the following NTSTATUS codes.

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
The listener object was created successfully and returned with the <i>*ppNdkListener</i> parameter.

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

The <i>NdkCreateListener</i> function creates an NDK listener object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkListener</i> parameter. If <i>NdkCreateListener</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>



<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>



<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>



<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_LISTENER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>