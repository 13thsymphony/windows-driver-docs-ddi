---
UID: NE.rilapitypes.RIL3GPP2TONE
title: RIL3GPP2TONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpp2tone_2.htm
old-project: netvista
ms.assetid: 306efd49-27ca-43d1-8f56-2f93c31be9a1
ms.author: windowsdriverdev
ms.date: 11/30/2017
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
req.alt-api: RIL3GPP2TONE
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

# RIL3GPP2TONE enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef enum _RIL3GPP2TONE { 
  RIL_3GPP2TONE_DIAL,
  RIL_3GPP2TONE_RINGBACK,
  RIL_3GPP2TONE_INTERCEPT,
  RIL_3GPP2TONE_ABRVINTERCEPT,
  RIL_3GPP2TONE_REORDER,
  RIL_3GPP2TONE_ABRVREORDER,
  RIL_3GPP2TONE_BUSY,
  RIL_3GPP2TONE_CONFIRM,
  RIL_3GPP2TONE_ANSWER,
  RIL_3GPP2TONE_CALLWAITING,
  RIL_3GPP2TONE_PIP,
  RIL_3GPP2TONE_MAX
} RIL3GPP2TONE;
````


## -enum-fields
<dl>

### -field RIL_3GPP2TONE_DIAL

<dd></dd>

### -field RIL_3GPP2TONE_RINGBACK

<dd></dd>

### -field RIL_3GPP2TONE_INTERCEPT

<dd></dd>

### -field RIL_3GPP2TONE_ABRVINTERCEPT

<dd></dd>

### -field RIL_3GPP2TONE_REORDER

<dd></dd>

### -field RIL_3GPP2TONE_ABRVREORDER

<dd></dd>

### -field RIL_3GPP2TONE_BUSY

<dd></dd>

### -field RIL_3GPP2TONE_CONFIRM

<dd></dd>

### -field RIL_3GPP2TONE_ANSWER

<dd></dd>

### -field RIL_3GPP2TONE_CALLWAITING

<dd></dd>

### -field RIL_3GPP2TONE_PIP

<dd></dd>

### -field RIL_3GPP2TONE_MAX

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