---
UID: NS.NDKPI._NDK_MR_DISPATCH
title: _NDK_MR_DISPATCH
author: windows-driver-content
description: The NDK_MR_DISPATCH structure specifies dispatch function entry points for the NDK memory region (MR) object.
old-location: netvista\ndk_mr_dispatch.htm
old-project: netvista
ms.assetid: C0EC5488-B08D-40A6-9E90-48E59B45B116
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDK_MR_DISPATCH, NDK_MR_DISPATCH
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
req.alt-api: NDK_MR_DISPATCH
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

# _NDK_MR_DISPATCH structure



## -description
The <b>NDK_MR_DISPATCH</b> structure specifies dispatch function entry points for the NDK memory region (MR) object.



## -syntax

````
typedef struct _NDK_MR_DISPATCH {
  NDK_FN_CLOSE_OBJECT                NdkCloseMr;
  NDK_FN_QUERY_EXTENSION_INTERFACE   NdkQueryExtension;
  NDK_FN_REGISTER_MR                 NdkRegisterMr;
  NDK_FN_DEREGISTER_MR               NdkDeregisterMr;
  NDK_FN_INITIALIZE_FAST_REGISTER_MR NdkInitializeFastRegisterMr;
  NDK_FN_GET_REMOTE_TOKEN_FROM_MR    NdkGetRemoteTokenFromMr;
  NDK_FN_GET_LOCAL_TOKEN_FROM_MR     NdkGetLocalTokenFromMr;
} NDK_MR_DISPATCH, *PNDK_MR_DISPATCH;
````


## -struct-fields

### -field NdkCloseMr

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkRegisterMr

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_register_mr.md">NDK_FN_REGISTER_MR</a> dispatch function.


### -field NdkDeregisterMr

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a> dispatch function.


### -field NdkInitializeFastRegisterMr

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_initialize_fast_register_mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a> dispatch function.


### -field NdkGetRemoteTokenFromMr

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_remote_token_from_mr.md">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a> dispatch function.


### -field NdkGetLocalTokenFromMr

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_local_token_from_mr.md">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a> dispatch function.


## -remarks
The <b>NDK_MR_DISPATCH</b> structure is used in the <a href="netvista.ndk_mr">NDK_MR</a> structure.


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
<a href="netvista.ndk_mr">NDK_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_deregister_mr.md">NDK_FN_DEREGISTER_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_remote_token_from_mr.md">NDK_FN_GET_REMOTE_TOKEN_FROM_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_local_token_from_mr.md">NDK_FN_GET_LOCAL_TOKEN_FROM_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_initialize_fast_register_mr.md">NDK_FN_INITIALIZE_FAST_REGISTER_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_register_mr.md">NDK_FN_REGISTER_MR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_MR_DISPATCH structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

