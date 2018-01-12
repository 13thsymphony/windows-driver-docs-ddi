---
UID: NS:ndkpi._NDK_CQ_DISPATCH
title: _NDK_CQ_DISPATCH
author: windows-driver-content
description: The NDK_CQ_DISPATCH structure specifies dispatch function entry points for the NDK completion queue (CQ) object.
old-location: netvista\ndk_cq_dispatch.htm
old-project: netvista
ms.assetid: 632E4FE8-BA03-4232-80E1-5EB3CC760D14
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _NDK_CQ_DISPATCH, NDK_CQ_DISPATCH
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
req.alt-api: NDK_CQ_DISPATCH
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
req.typenames: NDK_CQ_DISPATCH
---

# _NDK_CQ_DISPATCH structure



## -description
The <b>NDK_CQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK completion queue (CQ) object.



## -syntax

````
typedef struct _NDK_CQ_DISPATCH {
  NDK_FN_CLOSE_OBJECT                    NdkCloseCq;
  NDK_FN_QUERY_EXTENSION_INTERFACE       NdkQueryExtension;
  NDK_FN_RESIZE_CQ                       NdkResizeCq;
  NDK_FN_ARM_CQ                          NdkArmCq;
  NDK_FN_GET_CQ_RESULTS                  NdkGetCqResults;
  NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION NdkControlCqInterruptModeration;
  NDK_FN_GET_CQ_RESULTS_EX               NdkGetCqResultsEx;
} NDK_CQ_DISPATCH, *PNDK_CQ_DISPATCH;
````


## -struct-fields

### -field NdkCloseCq

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.


### -field NdkQueryExtension

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkResizeCq

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_resize_cq.md">NDK_FN_RESIZE_CQ</a> dispatch function.


### -field NdkArmCq

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_arm_cq.md">NDK_FN_ARM_CQ</a> dispatch function.


### -field NdkGetCqResults

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results.md">NDK_FN_GET_CQ_RESULTS</a> dispatch function.


### -field NdkControlCqInterruptModeration

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_control_cq_interrupt_moderation.md">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a> dispatch function.


### -field NdkGetCqResultsEx

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results_ex.md">NDK_FN_GET_CQ_RESULTS_EX</a> dispatch function. 

<b>Note</b>  This member is supported only in NDKPI 1.2 (Windows Server 2012 R2) and later.


## -remarks
The <b>NDK_CQ_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a> structure.


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
<a href="..\ndkpi\ns-ndkpi-_ndk_cq.md">NDK_CQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_arm_cq.md">NDK_FN_ARM_CQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_control_cq_interrupt_moderation.md">NDK_FN_CONTROL_CQ_INTERRUPT_MODERATION</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_cq_results.md">NDK_FN_GET_CQ_RESULTS</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_resize_cq.md">NDK_FN_RESIZE_CQ</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_CQ_DISPATCH structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

