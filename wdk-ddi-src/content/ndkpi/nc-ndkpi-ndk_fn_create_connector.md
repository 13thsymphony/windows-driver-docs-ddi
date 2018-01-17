---
UID: NC:ndkpi.NDK_FN_CREATE_CONNECTOR
title: NDK_FN_CREATE_CONNECTOR
author: windows-driver-content
description: The NdkCreateConnector (NDK_FN_CREATE_CONNECTOR) function creates an NDK connector object.
old-location: netvista\ndk_fn_create_connector.htm
old-project: netvista
ms.assetid: E800AC7B-EAEB-44FB-96ED-890C6442F066
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkCreateConnector
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
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CREATE_CONNECTOR callback



## -description
The <i>NdkCreateConnector</i> (<i>NDK_FN_CREATE_CONNECTOR</i>) function creates an NDK connector object.



## -prototype

````
NDK_FN_CREATE_CONNECTOR NdkCreateConnector;

NTSTATUS NdkCreateConnector(
  _In_     NDK_ADAPTER              *pNdkAdapter,
  _In_     NDK_FN_CREATE_COMPLETION CreateCompletion,
  _In_opt_ PVOID                    RequestContext,
           _Outptr_ NDK_CONNECTOR   **ppNdkConnector
)
{ ... }
````


## -parameters

### -param pNdkAdapter [in]

A pointer to an NDK adapter object (<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>).


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


### -param ppNdkConnector 

A pointer to an NDK connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If <i>NdkCreateConnector</i> returns STATUS_PENDING  this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns
The 
     <i>NdkCreateConnector</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The connector was created successfully and returned with the <i>*ppNdkConnector</i> parameter.
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
The <i>NdkCreateConnector</i> function creates an NDK connector object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkConnector</i> parameter. If <i>NdkCreateConnector</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.


## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_CONNECTOR callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

