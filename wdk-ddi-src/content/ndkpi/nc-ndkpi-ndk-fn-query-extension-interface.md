---
UID: NC.ndkpi.NDK_FN_QUERY_EXTENSION_INTERFACE
title: NDK_FN_QUERY_EXTENSION_INTERFACE
author: windows-driver-content
description: The NdkQqueryExtensionInterface (NDK_FN_QUERY_EXTENSION_INTERFACE) function gets information about an NDK extension interface.
old-location: netvista\ndk_fn_query_extension_interface.htm
old-project: netvista
ms.assetid: 439C990E-6978-4D0F-8453-6EB2FED1DB77
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkQqueryExtensionInterface
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

# NDK_FN_QUERY_EXTENSION_INTERFACE callback



## -description
<p>The <i>NdkQqueryExtensionInterface</i> (<i>NDK_FN_QUERY_EXTENSION_INTERFACE</i>) function gets information about an NDK extension interface.</p>


## -prototype

````
NDK_FN_QUERY_EXTENSION_INTERFACE NdkQqueryExtensionInterface;

NTSTATUS NdkQqueryExtensionInterface(
  _In_  NDK_OBJECT_HEADER       *pNdkObject,
  _In_  GUID                    *ExtensionInterfaceID,
  _In_  NDK_VERSION             ExtensionInterfaceVersion,
  _Out_ NDK_EXTENSION_INTERFACE *pExtensionInterface
)
{ ... }
````


## -parameters
<dl>

### -param <i>pNdkObject</i> [in]

<dd>
<p>	A pointer to the object header (<a href="..\ndkpi\ns-ndkpi--ndk-object-header.md">NDK_OBJECT_HEADER</a>) for the object being queried.</p>
</dd>

### -param <i>ExtensionInterfaceID</i> [in]

<dd>
<p>A pointer to the GUID that identifies the extension interface.</p>
</dd>

### -param <i>ExtensionInterfaceVersion</i> [in]

<dd>
<p>	The requested version (<a href="netvista.ndk_version">NDK_VERSION</a>) of the extension interface.
</p>
</dd>

### -param <i>pExtensionInterface</i> [out]

<dd>
<p>A pointer to an   <a href="..\ndkpi\ns-ndkpi--ndk-extension-interface.md">NDK_EXTENSION_INTERFACE</a> structure that the provider  initialized if the function returns STATUS_SUCCESS.</p>
</dd>
</dl>

## -returns
<p>The <i>NdkQqueryExtensionInterface</i> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The function is not supported.</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. </p>

<p> </p>

## -remarks
<p>Each NDK object contains an <i>NdkQqueryExtensionInterface</i> (<i>NDK_FN_QUERY_EXTENSION_INTERFACE</i>) function pointer in its object type-specific function dispatch table.  <i>NdkQqueryExtensionInterface</i> queries extended interfaces that are supported by the object type. There are currently no standard extended interfaces defined. An extension interface is identified by a GUID and represented as a pointer to a function dispatch table.</p>

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
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-adapter-dispatch.md">NDK_ADAPTER_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-connector-dispatch.md">NDK_CONNECTOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-cq-dispatch.md">NDK_CQ_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-extension-interface.md">NDK_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-query-extension-interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-object-header.md">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndk_version">NDK_VERSION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_QUERY_EXTENSION_INTERFACE callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
