---
UID: NS.ndkpi._NDK_SRQ_DISPATCH
title: NDK_SRQ_DISPATCH
author: windows-driver-content
description: The NDK_SRQ_DISPATCH structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.
old-location: netvista\ndk_srq_dispatch.htm
old-project: netvista
ms.assetid: 13297898-A72B-4771-A022-FDCBC281CEA0
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NDK_SRQ_DISPATCH, NDK_SRQ_DISPATCH
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
req.alt-api: NDK_SRQ_DISPATCH
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
req.iface: 
---

# NDK_SRQ_DISPATCH structure



## -description
<p>The <b>NDK_SRQ_DISPATCH</b> structure specifies dispatch function entry points for the NDK shared receive queue (SRQ) object.</p>


## -syntax

````
typedef struct _NDK_SRQ_DISPATCH {
  NDK_FN_CLOSE_OBJECT              NdkCloseSrq;
  NDK_FN_QUERY_EXTENSION_INTERFACE NdkQueryExtension;
  NDK_FN_MODIFY_SRQ                NdkModifySrq;
  NDK_FN_SRQ_RECEIVE               NdkSrqReceive;
} NDK_SRQ_DISPATCH;
````


## -struct-fields
<dl>

### -field <b>NdkCloseSrq</b>

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-close-object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.</p>
</dd>

### -field <b>NdkQueryExtension</b>

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-query-extension-interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.</p>
</dd>

### -field <b>NdkModifySrq</b>

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-modify-srq.md">NDK_FN_MODIFY_SRQ</a> dispatch function.</p>
</dd>

### -field <b>NdkSrqReceive</b>

<dd>
<p>The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk-fn-srq-receive.md">NDK_FN_SRQ_RECEIVE</a> dispatch function.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDK_SRQ_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi--ndk-srq.md">NDK_SRQ</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ndkpi\ns-ndkpi--ndk-srq.md">NDK_SRQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-close-object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-modify-srq.md">NDK_FN_MODIFY_SRQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-query-extension-interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-srq-receive.md">NDK_FN_SRQ_RECEIVE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_SRQ_DISPATCH structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
