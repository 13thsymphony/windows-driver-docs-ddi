---
UID : NC:ndkpi.NDK_FN_RECEIVE
title : NDK_FN_RECEIVE
author : windows-driver-content
description : The NdkReceive (NDK_FN_RECEIVE) function posts a receive request on an NDK queue pair (QP).
old-location : netvista\ndk_fn_receive.htm
old-project : netvista
ms.assetid : DC40C6B5-3F52-4A7E-B8FC-917ACDF8309A
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndk_fn_receive, NdkReceive callback function [Network Drivers Starting with Windows Vista], NdkReceive, NDK_FN_RECEIVE, NDK_FN_RECEIVE, ndkpi/NdkReceive
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
req.typenames : NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---


# NDK_FN_RECEIVE callback function
The <i>NdkReceive</i> (<i>NDK_FN_RECEIVE</i>) function posts a receive request on an NDK queue pair (QP).

## Syntax

```
NDK_FN_RECEIVE NdkFnReceive;

NTSTATUS NdkFnReceive(
  NDK_QP *pNdkQp,
  PVOID RequestContext,
  CONST NDK_SGE,
  ULONG nSge
)
{...}
```

## Parameters

`*pNdkQp`

A pointer to an NDK queue pair (QP) object
(<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>).

`RequestContext`

A context value to be returned in the <b>RequestContext</b> member of the <a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a> structure for this request.

`NDK_SGE`



`nSge`

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


## Return Value

The 
     <i>NdkReceive</i> function returns one of the following NTSTATUS codes.
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
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. 

</td>
</tr>
</table>

## Remarks

<i>NdkReceive</i> posts a receive request on a queue pair (QP).

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

<a href="..\ndkpi\ns-ndkpi-_ndk_qp.md">NDK_QP</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_result.md">NDK_RESULT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_RECEIVE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>