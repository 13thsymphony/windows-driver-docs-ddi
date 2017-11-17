---
UID: NE.wdftypes._WDF_TRI_STATE
title: WDF_TRI_STATE
author: windows-driver-content
description: The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.
old-location: wdf\wdf_tri_state.htm
ms.assetid: 8ea6e373-225d-4fcd-abcf-c19b07f9f5d8
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: enum
ms.prod: windows-hardware
ms.technology: wdf
req.header: wdftypes.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.alt-api: WDF_TRI_STATE
req.alt-loc: wdftypes.h,wudfddi_types.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
ms.keywords: WDF_TIMER_CONFIG, WDF_TIMER_CONFIG, *PWDF_TIMER_CONFIG
req.iface: 
req.product: Windows 10 or later.
---

# WDF_TRI_STATE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.</p>


## -syntax

````
typedef enum _WDF_TRI_STATE { 
  WdfFalse       = FALSE,
  WdfTrue        = TRUE,
  WdfUseDefault  = 2
} WDF_TRI_STATE, *PWDF_TRI_STATE;
````


## -enum-fields
<dl>

### -field <a id="WdfFalse"></a><a id="wdffalse"></a><a id="WDFFALSE"></a><b>WdfFalse</b>

<dd>
<p>The meaning of this enumerator is specific to its use as a structure member or function parameter.</p>
</dd>

### -field <a id="WdfTrue"></a><a id="wdftrue"></a><a id="WDFTRUE"></a><b>WdfTrue</b>

<dd>
<p>The meaning of this enumerator is specific to its use as a structure member or function parameter.</p>
</dd>

### -field <a id="WdfUseDefault"></a><a id="wdfusedefault"></a><a id="WDFUSEDEFAULT"></a><b>WdfUseDefault</b>

<dd>
<p>The meaning of this enumerator is specific to its use as a structure member or function parameter.</p>
</dd>
</dl>

## -remarks
<p>The WDF_TRI_STATE enumeration type is available in version 1.0 and later versions of KMDF.</p>

<p>The WDF_TRI_STATE enumeration type is available in version 1.0 and later versions of KMDF.</p>

<p>The WDF_TRI_STATE enumeration type is available in version 1.0 and later versions of KMDF.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.11</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdftypes.h (include Wdf.h); </dt>
<dt>Wudfddi_types.h</dt>
</dl>
</td>
</tr>
</table>