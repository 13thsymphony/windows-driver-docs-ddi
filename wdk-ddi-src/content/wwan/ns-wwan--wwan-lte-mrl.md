---
UID: NS.wwan._WWAN_LTE_MRL
title: WWAN_LTE_MRL
author: windows-driver-content
description: The WWAN_LTE_MRL structure represents the measured results list (MRL) of neighboring LTE cells.
old-location: netvista\wwan_lte_mrl.htm
old-project: netvista
ms.assetid: 5959B7A7-147D-4F20-82CC-EC1DEAAE3494
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WWAN_LTE_MRL, WWAN_LTE_MRL, *PWWAN_LTE_MRL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_LTE_MRL
req.alt-loc: wwan.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# WWAN_LTE_MRL structure



## -description
<p>The <b>WWAN_LTE_MRL</b> structure represents the measured results list (MRL) of neighboring LTE cells.</p>


## -syntax

````
typedef struct _WWAN_LTE_MRL {
  ULONG ElementCount;
  BYTE  LTEMrl[ANYSIZE_ARRAY];
} WWAN_LTE_MRL, *PWWAN_LTE_MRL;
````


## -struct-fields
<dl>

### -field <b>ElementCount</b>

<dd>
<p>The count of MRL entries following this member.</p>
</dd>

### -field <b>LTEMrl[ANYSIZE_ARRAY]</b>

<dd>
<p>The array of MRL records, each specified as a <a href="..\wwan\ns-wwan--wwan-lte-mrl-info.md">WWAN_LTE_MRL_INFO</a> structure.</p>
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
<p>Windows 10, version 1709</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan--wwan-base-stations-info.md">WWAN_BASE_STATIONS_INFO</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan--wwan-lte-mrl-info.md">WWAN_LTE_MRL_INFO</a>
</dt>
<dt>
<a href="..\wwan\ns-wwan--wwan-lte-serving-cell-info.md">WWAN_LTE_SERVING_CELL_INFO</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-base-stations-information-query-support">MB base stations information query support</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_LTE_MRL structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
