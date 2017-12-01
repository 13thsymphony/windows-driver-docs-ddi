---
UID: NS.ndiswwan._NDIS_WWAN_GET_VISIBLE_PROVIDERS
title: NDIS_WWAN_GET_VISIBLE_PROVIDERS
author: windows-driver-content
description: The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers.
old-location: netvista\ndis_wwan_get_visible_providers.htm
old-project: netvista
ms.assetid: C1AF383A-2D9D-4B2F-A925-D138E1B7AA4F
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NDIS_WWAN_GET_VISIBLE_PROVIDERS, NDIS_WWAN_GET_VISIBLE_PROVIDERS, *PNDIS_WWAN_GET_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_GET_VISIBLE_PROVIDERS
req.alt-loc: ndiswwan.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NDIS_WWAN_GET_VISIBLE_PROVIDERS structure



## -description
<p>The NDIS_WWAN_GET_VISIBLE_PROVIDERS structure is used to request the miniport driver get either all visible providers or only multi-carrier visible providers.</p>


## -syntax

````
typedef struct _NDIS_WWAN_GET_VISIBLE_PROVIDERS {
  NDIS_OBJECT_HEADER         Header;
  WWAN_GET_VISIBLE_PROVIDERS VisibleProviders;
} NDIS_WWAN_GET_VISIBLE_PROVIDERS, *PNDIS_WWAN_GET_VISIBLE_PROVIDERS;
````


## -struct-fields
<dl>

### -field <b>Header</b>

<dd>
<p>The header with type, revision, and size information about the NDIS_WWAN_GET_VISIBLE_PROVIDERS
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     </p>
<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
<p>Type</p>
</td>
<td>
<p>NDIS_OBJECT_TYPE_DEFAULT</p>
</td>
</tr>
<tr>
<td>
<p>Revision</p>
</td>
<td>
<p>NDIS_WWAN_GET_VISIBLE_PROVIDERS_REVISION_1</p>
</td>
</tr>
<tr>
<td>
<p>Size</p>
</td>
<td>
<p>sizeof(NDIS_WWAN_GET_VISIBLE_PROVIDERS)</p>
</td>
</tr>
</table>
<p> </p>
<p>For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field <b>VisibleProviders</b>

<dd>
<p>A formatted WWAN_GET_VISIBLE_PROVIDERS object that provides additional information to the miniport about the type of providers to return.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with  Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndiswwan.h (include Ndiswwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan--wwan-get-visible-providers.md">WWAN_GET_VISIBLE_PROVIDERS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_GET_VISIBLE_PROVIDERS structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
