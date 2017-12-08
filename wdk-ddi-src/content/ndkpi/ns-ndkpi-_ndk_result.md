---
UID: NS.NDKPI._NDK_RESULT
title: _NDK_RESULT
author: windows-driver-content
description: The NDK_RESULT structure returns the results for an NDK request operation.
old-location: netvista\ndk_result.htm
old-project: netvista
ms.assetid: B7898C81-E90D-4210-BEAE-1E629FCD7195
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDK_RESULT, NDK_RESULT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_RESULT
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

# _NDK_RESULT structure



## -description
The <b>NDK_RESULT</b> structure returns the results for an NDK request operation. 


## -syntax

````
typedef struct _NDK_RESULT {
  NTSTATUS Status;
  ULONG    BytesTransferred;
  PVOID    QPContext;
  PVOID    RequestContext;
} NDK_RESULT;
````


## -struct-fields

### -field Status

The NDK request completion status.

### -field BytesTransferred

The number of bytes transferred. The value of this member  is valid only for <i>NdkReceive</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_receive.md">NDK_FN_RECEIVE</a>) request completions. The member is undefined for all other NDK request completions.

### -field QPContext

A context value for all requests that are posted over a queue pair (QP). The NDK consumer specified this  pointer when it called the <i>NdkCreateQp</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a>) function to create the <a href="netvista.ndk_qp">NDK_QP</a> object.

### -field RequestContext

A request context value specified by the NDK consumer when  a request is posted.

## -remarks
 The <i>NdkGetCqResults</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results.md">NDK_FN_GET_CQ_RESULTS</a>)  function gets an array of <b>NDK_RESULT</b> structures that are filled with completion results that were removed from the CQ.



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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results.md">NDK_FN_GET_CQ_RESULTS</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_receive.md">NDK_FN_RECEIVE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_RESULT structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
