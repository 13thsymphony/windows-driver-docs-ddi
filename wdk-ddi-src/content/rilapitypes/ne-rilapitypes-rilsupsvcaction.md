---
UID: NE.rilapitypes.RILSUPSVCACTION
title: RILSUPSVCACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcaction_2.htm
old-project: netvista
ms.assetid: 776db7b4-aa53-489d-9358-387e29e4e3e1
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: RIL_WritePhonebookEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSUPSVCACTION
req.alt-loc: rilapitypes.h
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

# RILSUPSVCACTION enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef enum _RILSUPSVCACTION { 
  RIL_SUPSVCACTION_DEACTIVATE,
  RIL_SUPSVCACTION_REGISTER,
  RIL_SUPSVCACTION_ERASE,
  RIL_SUPSVCACTION_INTERROGATE,
  RIL_SUPSVCACTION_REGISTER_PW,
  RIL_SUPSVCACTION_USSD,
  RIL_SUPSVCACTION_MAX
} RILSUPSVCACTION;
````


## -enum-fields
<dl>

### -field <a id="RIL_SUPSVCACTION_DEACTIVATE"></a><a id="ril_supsvcaction_deactivate"></a><b>RIL_SUPSVCACTION_DEACTIVATE</b>

<dd></dd>

### -field <a id="RIL_SUPSVCACTION_REGISTER"></a><a id="ril_supsvcaction_register"></a><b>RIL_SUPSVCACTION_REGISTER</b>

<dd></dd>

### -field <a id="RIL_SUPSVCACTION_ERASE"></a><a id="ril_supsvcaction_erase"></a><b>RIL_SUPSVCACTION_ERASE</b>

<dd></dd>

### -field <a id="RIL_SUPSVCACTION_INTERROGATE"></a><a id="ril_supsvcaction_interrogate"></a><b>RIL_SUPSVCACTION_INTERROGATE</b>

<dd></dd>

### -field <a id="RIL_SUPSVCACTION_REGISTER_PW"></a><a id="ril_supsvcaction_register_pw"></a><b>RIL_SUPSVCACTION_REGISTER_PW</b>

<dd></dd>

### -field <a id="RIL_SUPSVCACTION_USSD"></a><a id="ril_supsvcaction_ussd"></a><b>RIL_SUPSVCACTION_USSD</b>

<dd></dd>

### -field <a id="RIL_SUPSVCACTION_MAX"></a><a id="ril_supsvcaction_max"></a><b>RIL_SUPSVCACTION_MAX</b>

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>