---
UID: NE.ntddrilapitypes.RILDISPLAYINFOTAG
title: RILDISPLAYINFOTAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfotag.htm
old-project: netvista
ms.assetid: ba47d9e3-4e95-479b-9e6a-10eb723e7d59
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: TUPLE_REQUEST, TUPLE_REQUEST, *PTUPLE_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILDISPLAYINFOTAG
req.alt-loc: ntddrilapitypes.h
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
---

# RILDISPLAYINFOTAG enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef enum _RILDISPLAYINFOTAG { 
  RIL_EXTENDED_DISPLAY_TAG_SKIP,
  RIL_EXTENDED_DISPLAY_TAG_CONTINUATION,
  RIL_EXTENDED_DISPLAY_TAG_CALLED_ADDRESS,
  RIL_EXTENDED_DISPLAY_TAG_CAUSE,
  RIL_EXTENDED_DISPLAY_TAG_PROGRESS_INDICATOR,
  RIL_EXTENDED_DISPLAY_TAG_NOTIFICATION_INDICATOR,
  RIL_EXTENDED_DISPLAY_TAG_PROMPT,
  RIL_EXTENDED_DISPLAY_TAG_ACCUMULATED_DIGITS,
  RIL_EXTENDED_DISPLAY_TAG_STATUS,
  RIL_EXTENDED_DISPLAY_TAG_INBAND,
  RIL_EXTENDED_DISPLAY_TAG_CALLING_ADDRESS,
  RIL_EXTENDED_DISPLAY_TAG_REASON,
  RIL_EXTENDED_DISPLAY_TAG_CALLING_PARTY_NAME,
  RIL_EXTENDED_DISPLAY_TAG_CALLED_PARTY_NAME,
  RIL_EXTENDED_DISPLAY_TAG_ORIGINAL_CALLED_NAME,
  RIL_EXTENDED_DISPLAY_TAG_REDIRECTING_NAME,
  RIL_EXTENDED_DISPLAY_TAG_CONNECTED_NAME,
  RIL_EXTENDED_DISPLAY_TAG_ORIGINATING_RESTRICT,
  RIL_EXTENDED_DISPLAY_TAG_DATE_TIME_OF_DAY,
  RIL_EXTENDED_DISPLAY_TAG_CALL_APPEARANCE_ID,
  RIL_EXTENDED_DISPLAY_TAG_FEATURE_ADDRESS,
  RIL_EXTENDED_DISPLAY_TAG_REDIRECTION_NAME,
  RIL_EXTENDED_DISPLAY_TAG_REDIRECTION_NUMBER,
  RIL_EXTENDED_DISPLAY_TAG_REDIRECTING_NUMBER,
  RIL_EXTENDED_DISPLAY_TAG_ORIGINAL_CALLED_NUMBER,
  RIL_EXTENDED_DISPLAY_TAG_CONNECTED_NUMBER,
  RIL_EXTENDED_DISPLAY_TAG_TEXT,
  RIL_EXTENDED_DISPLAY_TAG_MAX
} RILDISPLAYINFOTAG;
````


## -enum-fields
<dl>

### -field RIL_EXTENDED_DISPLAY_TAG_SKIP

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CONTINUATION

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CALLED_ADDRESS

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CAUSE

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_PROGRESS_INDICATOR

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_NOTIFICATION_INDICATOR

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_PROMPT

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_ACCUMULATED_DIGITS

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_STATUS

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_INBAND

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CALLING_ADDRESS

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_REASON

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CALLING_PARTY_NAME

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CALLED_PARTY_NAME

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_ORIGINAL_CALLED_NAME

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_REDIRECTING_NAME

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CONNECTED_NAME

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_ORIGINATING_RESTRICT

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_DATE_TIME_OF_DAY

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CALL_APPEARANCE_ID

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_FEATURE_ADDRESS

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_REDIRECTION_NAME

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_REDIRECTION_NUMBER

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_REDIRECTING_NUMBER

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_ORIGINAL_CALLED_NUMBER

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_CONNECTED_NUMBER

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_TEXT

<dd></dd>

### -field RIL_EXTENDED_DISPLAY_TAG_MAX

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
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>