---
UID: NC:ndis.IF_QUERY_OBJECT
title: IF_QUERY_OBJECT
author: windows-driver-content
description: The ProviderQueryObject function retrieves information about a network interface.
old-location: netvista\providerqueryobject.htm
old-project: netvista
ms.assetid: dea90ff0-7620-4364-90dc-2dc5d2e34ce1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.providerqueryobject, ProviderQueryObject callback function [Network Drivers Starting with Windows Vista], ProviderQueryObject, IF_QUERY_OBJECT, IF_QUERY_OBJECT, ndis/ProviderQueryObject, *IFP_QUERY_OBJECT callback function [Network Drivers Starting with Windows Vista], *IFP_QUERY_OBJECT, net_if_provider_functions_ref_8e4d405f-cae0-40bc-8d9d-6d85e5c7ff06.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	*IFP_QUERY_OBJECT
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# IF_QUERY_OBJECT function
The 
  <i>ProviderQueryObject</i> function retrieves information about a network interface.

## Syntax

```
IF_QUERY_OBJECT IfQueryObject;

NDIS_STATUS() IfQueryObject(
  NDIS_HANDLE ProviderIfContext,
  NET_IF_OBJECT_ID ObjectId,
  PULONG pOutputBufferLength,
  PVOID pOutputBuffer
)
{...}
```

## Parameters

`ProviderIfContext`

A handle that identifies the interface provider's context area for the interface. The interface
     provider passed this handle to NDIS in a call to the 
     <a href="..\ndis\nf-ndis-ndisifregisterinterface.md">
     NdisIfRegisterInterface</a> function.

`ObjectId`

An identifier for the object that is the target of the query request. For a list of object
     identifiers (OIDs) that apply to interface providers, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface
     OIDs</a>.

`pOutputBufferLength`

A pointer to an NDIS-supplied variable in which NDIS provides the length of the output buffer. 
     <i>ProviderQueryObject</i> writes the length of the data that it put in the output buffer.

`pOutputBuffer`

A pointer to an NDIS-supplied output buffer in which 
     <i>ProviderQueryObject</i> writes the response to the query request.


## Return Value

<i>ProviderQueryObject</i> returns one of the following status values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The call failed because some of the input parameters were invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>Xxx</i></b></dt>
</dl>
</td>
<td width="60%">
The call failed for some other reason. This function can propagate error codes from the
       functions that it calls or generate an appropriate error code.

</td>
</tr>
</table>

## Remarks

NDIS calls a network interface provider's 
    <i>ProviderQueryObject</i> function to obtain information about an interface that the provider registered.
    For a list of OIDs that apply to interface providers, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface OIDs</a>.

NDIS calls 
    <i>ProviderQueryObject</i> at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Target Platform** | Windows |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ndis\nf-ndis-ndisifregisterinterface.md">NdisIfRegisterInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20IF_QUERY_OBJECT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>