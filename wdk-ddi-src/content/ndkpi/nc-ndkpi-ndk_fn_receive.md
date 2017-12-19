---
UID: NC.ndkpi.NDK_FN_RECEIVE
title: NDK_FN_RECEIVE
author: windows-driver-content
description: The NdkReceive (NDK_FN_RECEIVE) function posts a receive request on an NDK queue pair (QP).
old-location: netvista\ndk_fn_receive.htm
old-project: NetVista
ms.assetid: DC40C6B5-3F52-4A7E-B8FC-917ACDF8309A
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
req.alt-api: NdkReceive
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

# NDK_FN_RECEIVE callback



## -description

   The <i>NdkReceive</i> (<i>NDK_FN_RECEIVE</i>) function posts a receive request on an NDK queue pair (QP).  
  



## -prototype

````
NDK_FN_RECEIVE NdkReceive;

NTSTATUS NdkReceive(
  _In_     NDK_QP                         *pNdkQp,
  _In_opt_ PVOID                          RequestContext,
           _In_reads_(nSge) CONST NDK_SGE *pSgl,
  _In_     ULONG                          nSge
)
{ ... }
````


## -parameters

### -param pNdkQp [in]

A pointer to an NDK queue pair (QP) object
(<a href="netvista.ndk_qp">NDK_QP</a>).


### -param RequestContext [in, optional]

A context value to be returned in the <b>RequestContext</b> member of the <a href="netvista.ndk_result">NDK_RESULT</a> structure for this request.



### -param pSgl 

An array of SGE structures (<a href="netvista.ndk_sge">NDK_SGE</a>) that represent the buffers to receive incoming data.



### -param nSge [in]

The number of SGE structures in the array  that is specified in the <i>pSgl</i>
parameter.


## -returns
The 
     <i>NdkReceive</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The request was posted successfully. A completion entry will be queued to the CQ when the work request is completed.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
<i>NdkReceive</i> posts a receive request on a queue pair (QP).


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
<a href="netvista.ndk_qp">NDK_QP</a>
</dt>
<dt>
<a href="netvista.ndk_result">NDK_RESULT</a>
</dt>
<dt>
<a href="netvista.ndk_sge">NDK_SGE</a>
</dt>
<dt>
<a href="netvista.ndkpi_work_request_posting_requirements">NDKPI Work Request Posting Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_RECEIVE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

