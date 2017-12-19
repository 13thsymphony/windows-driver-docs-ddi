---
UID: NC.ndkpi.NDK_FN_CREATE_MW
title: NDK_FN_CREATE_MW
author: windows-driver-content
description: The NdkCreateMw (NDK_FN_CREATE_MW) function creates an NDK memory window (MW) object.
old-location: netvista\ndk_fn_create_mw.htm
old-project: NetVista
ms.assetid: BAE0DF74-19AB-4AE9-A28C-C1CC2F569D1F
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
req.alt-api: NdkCreateMw
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

# NDK_FN_CREATE_MW callback



## -description
The <i>NdkCreateMw</i> (<i>NDK_FN_CREATE_MW</i>) function creates an NDK memory window (MW) object.



## -prototype

````
NDK_FN_CREATE_MW NdkCreateMw;

NTSTATUS NdkCreateMw(
  _In_     NDK_PD                   *pNdkPd,
  _In_     NDK_FN_CREATE_COMPLETION CreateCompletion,
  _In_opt_ PVOID                    RequestContext,
           _Outptr_ NDK_MW          **ppNdkMw
)
{ ... }
````


## -parameters

### -param pNdkPd [in]

A pointer to an NDK protection domain (PD) object (<a href="netvista.ndk_pd">NDK_PD</a>).


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


### -param ppNdkMw 

A pointer to a created MW object (<a href="netvista.ndk_mw">NDK_MW</a>) is returned in this location if  the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns
The 
     <i>NdkCreateMw</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The MW object was created successfully and returned with the <i>*ppNdkMw</i> parameter.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The request failed due to insufficient resources. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
The <i>NdkCreateMw</i> function creates an  NDK memory window (MW) object that can be used for bind requests. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkMw</i> parameter. If <i>NdkCreateMw</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.


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
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="netvista.ndk_mw">NDK_MW</a>
</dt>
<dt>
<a href="netvista.ndk_pd">NDK_PD</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_CREATE_MW callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

