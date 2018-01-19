---
UID : NC:ndkpi.NDK_FN_GET_PEER_ADDRESS
title : NDK_FN_GET_PEER_ADDRESS
author : windows-driver-content
description : The NdkGetPeerAddress (NDK_FN_GET_PEER_ADDRESS) function returns the remote address for an NDK connection.
old-location : netvista\ndk_fn_get_peer_address.htm
old-project : netvista
ms.assetid : 7015FBC6-BACD-4154-A6E5-15A949BA5906
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
req.alt-api : NdkGetPeerAddress
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


# NDK_FN_GET_PEER_ADDRESS callback function
The <i>NdkGetPeerAddress</i> (<i>NDK_FN_GET_PEER_ADDRESS</i>) function returns the remote address for an NDK connection.

## Syntax

```
NDK_FN_GET_PEER_ADDRESS NdkFnGetPeerAddress;

NTSTATUS NdkFnGetPeerAddress(
  NDK_CONNECTOR *pNdkConnector,
  PSOCKADDR pAddress,
  ULONG *pAddressLength
)
{...}
```

## Parameters

`*pNdkConnector`



`pAddress`

A remote address is returned in this buffer.

`*pAddressLength`




## Return Value

The 
     <i>NdkGetPeerAddress</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>A remote address was written to the buffer in the <i>pAddress</i> parameter.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer size specified in the <i>*pAddressLength</i> parameter input is too small. <i>*pAddressLength</i> output value is updated with the required buffer size.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

## Remarks

<i>NdkGetPeerAddress</i> returns the remote address for a connection.

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
<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_PEER_ADDRESS callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>