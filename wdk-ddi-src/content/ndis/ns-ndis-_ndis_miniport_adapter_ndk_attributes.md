---
UID: NS.NDIS._NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
author: windows-driver-content
description: The NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure specifies the NDK-capabilities of a miniport adapter. This structure is used in the NDKAttributes member of the NDIS_MINIPORT_ADAPTER_ATTRIBUTES union.
old-location: netvista\ndis_miniport_adapter_ndk_attributes.htm
old-project: netvista
ms.assetid: 615A190E-D8F5-4E84-A475-FFF38077BC09
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
---

# _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure



## -description
The <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b> structure specifies the NDK-capabilities of a miniport adapter. This structure is used in the <b>NDKAttributes</b> member of the <a href="netvista.ndis_miniport_adapter_attributes">NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a> union.


## -syntax

````
typedef struct _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES {
  NDIS_OBJECT_HEADER     Header;
  BOOLEAN                Enabled;
  PNDIS_NDK_CAPABILITIES NdkCapabilities;
} NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES;
````


## -struct-fields

### -field Header

A <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b> structure. 

Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:
<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to <b>NDIS_SIZEOF_MINIPORT_ADAPTER_NDK_ATTRIBUTES_REVISION_1</b>.</li>
</ul>

### -field Enabled

If the miniport adapter's NDK functionality is enabled, this member is <b>TRUE</b>. Otherwise, it is <b>FALSE</b>.

### -field NdkCapabilities

A pointer to an <a href="netvista.ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a> structure that specifies the capabilities of an NDK adapter.  

## -remarks
An NDK-capable adapter must indicate its NDK capabilities in its <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function, even if its NDK functionality is currently disabled.

To report its NDK capabilities, the miniport adapter stores an  <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b> structure in the <b>NDKAttributes</b> member of the <a href="netvista.ndis_miniport_adapter_attributes">NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a> union and passes  the <b>NDIS_MINIPORT_ADAPTER_ATTRIBUTES</b> union  to the <a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a> function. For more information, see <a href="netvista.initializing_an_ndk_miniport_adapter">Initializing an NDK Miniport Adapter</a>.

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
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_adapter_attributes">NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="netvista.initializing_an_ndk_miniport_adapter">Initializing an NDK Miniport Adapter</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
