---
UID : NC:ndkpi.NDK_FN_QUERY_ADAPTER_INFO
title : NDK_FN_QUERY_ADAPTER_INFO
author : windows-driver-content
description : The NdkQueryAdapterInfo (NDK_FN_QUERY_ADAPTER_INFO) function retrieves information about limits and capabilities of an NDK adapter.
old-location : netvista\ndk_fn_query_adapter_info.htm
old-project : netvista
ms.assetid : A307584E-CBF6-4CEB-8A0F-D519DA7599D3
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndk_fn_query_adapter_info, NdkQueryAdapterInfo callback function [Network Drivers Starting with Windows Vista], NdkQueryAdapterInfo, NDK_FN_QUERY_ADAPTER_INFO, NDK_FN_QUERY_ADAPTER_INFO, ndkpi/NdkQueryAdapterInfo
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---


# NDK_FN_QUERY_ADAPTER_INFO callback function
The <i>NdkQueryAdapterInfo</i> (<i>NDK_FN_QUERY_ADAPTER_INFO</i>) function retrieves information about limits and capabilities of an  NDK adapter.

## Syntax

```
NDK_FN_QUERY_ADAPTER_INFO NdkFnQueryAdapterInfo;

NTSTATUS NdkFnQueryAdapterInfo(
  NDK_ADAPTER *pNdkAdapter,
  NDK_ADAPTER_INFO *pInfo,
  ULONG *pBufferSize
)
{...}
```

## Parameters

`*pNdkAdapter`

A pointer to an NDK adapter (<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER)</a> instance.

`*pInfo`

A pointer to a buffer that contains an <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure. If the request completes with STATUS_SUCCESS, the NDK provider  fills  the structure with adapter information.

`*pBufferSize`

On input, this parameter is a pointer to a variable that holds the size, in bytes, of the buffer that the  <i>pInfo</i> parameter  points to. On output, the variable receives the size, in bytes,  of the adapter information that was written into the buffer.


## Return Value

The 
     <i>NdkQueryAdapterInfo</i> function returns one of the following NTSTATUS codes.
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
The 	request completed successfully.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">

The value in the <i>*pBufferSize</i> parameter specified a buffer size that was too small to hold the adapter information. <i>*pBufferSize</i> is updated with the required size.


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

<i>NdkQueryAdapterInfo</i> retrieves the adapter information in an  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a> structure. The structure  contains information on various limits and capabilities of the adapter.

<i>NdkQueryAdapterInfo</i>  requires an IRQL equal to PASSIVE_LEVEL and  it blocks until the request is completed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Target Platform** | Windows |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439851">NDK_ADAPTER_INFO</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_QUERY_ADAPTER_INFO callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>