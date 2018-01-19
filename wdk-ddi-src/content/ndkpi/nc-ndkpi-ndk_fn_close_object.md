---
UID : NC:ndkpi.NDK_FN_CLOSE_OBJECT
title : NDK_FN_CLOSE_OBJECT
author : windows-driver-content
description : The NdkCloseObject (NDK_FN_CLOSE_OBJECT) function initiates a close request for an NDK object.
old-location : netvista\ndk_fn_close_object.htm
old-project : netvista
ms.assetid : 9547DCCE-6B3C-434F-A8CA-1AA59AB7152A
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api : NdkCloseObject
req.alt-loc : ndkpi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---


# NDK_FN_CLOSE_OBJECT callback function
The <i>NdkCloseObject</i> (<i>NDK_FN_CLOSE_OBJECT</i>) function initiates a close request for an NDK  object.

## Syntax

```
NDK_FN_CLOSE_OBJECT NdkFnCloseObject;

NTSTATUS NdkFnCloseObject(
  NDK_OBJECT_HEADER *pNdkObject,
  NDK_FN_CLOSE_COMPLETION CloseCompletion,
  PVOID RequestContext
)
{...}
```

## Parameters

`*pNdkObject`



`CloseCompletion`

A pointer to an <i>NdkCloseCompletion</i> close completion callback function  (<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_completion.md">NDK_FN_CLOSE_COMPLETION</a>).

`RequestContext`

A context value for the NDK provider to pass back to the <i>NdkCloseCompletion</i> function that is specified in the <i>CloseCompletion</i> parameter.


## Return Value

The 
     <i>NdkCloseObject</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The NDK object is closed. The provider will not call the <i>NdkCloseCompletion</i>  function.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The  request  is pending,  the provider will call the <i>NdkCloseCompletion</i> function to complete the operation asynchronously. The close request has been successfully initiated, but it might not be completed. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

## Remarks

The function dispatch table for each  type of NDK object   includes  an <i>NDK_FN_CLOSE_OBJECT</i> function pointer. Close  requests are asynchronous. An  NDK consumer must not access the object after a close request is started. 

The NDK provider must ensure that the <i>NdkCloseCompletion</i> function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_completion.md">NDK_FN_CLOSE_COMPLETION</a>) is the last callback called for the object that is closing. The provider must ensure that all outstanding asynchronous requests are completed and all in-progress callbacks have returned and further callbacks are prevented before the provider calls the <i>NdkCloseCompletion</i> function.   After the provider calls the <i>NdkCloseCompletion</i> function, the provider not call any  completion functions or notification callback functions  for the object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_cq_dispatch.md">NDK_CQ_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_completion.md">NDK_FN_CLOSE_COMPLETION</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_object_header.md">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CLOSE_OBJECT callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>