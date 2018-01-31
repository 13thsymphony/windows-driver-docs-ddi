---
UID : NC:ndkpi.NDK_FN_INITIALIZE_FAST_REGISTER_MR
title : NDK_FN_INITIALIZE_FAST_REGISTER_MR
author : windows-driver-content
description : The NdkInitializeFastRegisterMr (NDK_FN_INITIALIZE_FAST_REGISTER_MR) function initializes an NDK memory region (MR) for fast registration.
old-location : netvista\ndk_fn_initialize_fast_register_mr.htm
old-project : netvista
ms.assetid : E5051F79-E523-4A2B-965F-4D2C3BB5847F
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndk_fn_initialize_fast_register_mr, NdkInitializeFastRegisterMr callback function [Network Drivers Starting with Windows Vista], NdkInitializeFastRegisterMr, NDK_FN_INITIALIZE_FAST_REGISTER_MR, NDK_FN_INITIALIZE_FAST_REGISTER_MR, ndkpi/NdkInitializeFastRegisterMr
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndkpi.h
req.include-header : Ndkpi.h
req.target-type : Windows
req.target-min-winverclnt : None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---


# NDK_FN_INITIALIZE_FAST_REGISTER_MR callback function
The <i>NdkInitializeFastRegisterMr</i> (<i>NDK_FN_INITIALIZE_FAST_REGISTER_MR</i>) function initializes an NDK memory region (MR) for fast registration.

## Syntax

```
NDK_FN_INITIALIZE_FAST_REGISTER_MR NdkFnInitializeFastRegisterMr;

NTSTATUS NdkFnInitializeFastRegisterMr(
  NDK_MR *pNdkMr,
  ULONG AdapterPageCount,
  BOOLEAN RemoteAccess,
  NDK_FN_REQUEST_COMPLETION RequestCompletion,
  PVOID RequestContext
)
{...}
```

## Parameters

`*pNdkMr`



`AdapterPageCount`

The maximum number of adapter pages to support in this MR such that fast-register work requests with equal or  a lower  number of adapter pages can be supported.

`RemoteAccess`

A BOOLEAN value that indicates if the MR must be initialized for remote access or not. An NDK consumer must set <i>RemoteAccess</i> to TRUE if the consumer will request remote access with  the <i>NdkFastRegister</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_fast_register.md">NDK_FN_FAST_REGISTER</a>) function.

`RequestCompletion`

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).

`RequestContext`

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## Return Value

The  
     <i>NdkInitializeFastRegisterMr</i> function returns one of the following NTSTATUS codes.
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
Initialization was completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
 The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IMPLEMENTATION_LIMIT</b></dt>
</dl>
</td>
<td width="60%">
The request failed because the adapter does not support the requested <i>AdapterPageCount</i>.

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

<i>NdkInitializeFastRegisterMr</i> initializes an MR for fast registration. The  <a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a> object must be created with <i>FastRegister</i> parameter of the <i>NdkCreateMr</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mr.md">NDK_FN_CREATE_MR</a>) function set to TRUE.

You can make multiple calls to <i>NdkInitializeFastRegisterMr</i>, either in parallel or one after another.

After <i>NdkInitializeFastRegisterMr</i> returns, a fast register work request can be posted to a queue pair (QP).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **Library** |  |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_mr.md">NDK_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_fast_register.md">NDK_FN_FAST_REGISTER</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mr.md">NDK_FN_CREATE_MR</a>

<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_INITIALIZE_FAST_REGISTER_MR callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>