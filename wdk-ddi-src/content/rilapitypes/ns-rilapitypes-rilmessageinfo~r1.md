---
UID: NS.rilapitypes.RILMESSAGEINFO~r1
title: RILMESSAGEINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinfo_2.htm
old-project: netvista
ms.assetid: db7b8526-e70a-4589-a128-58641c865d58
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILMESSAGEINFO,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMESSAGEINFO
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

# RILMESSAGEINFO structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILMESSAGEINFO {
  DWORD             cbSize;
  HUICCAPP          hUiccApp;
  DWORD             dwParams;
  DWORD             dwIndex;
  RILMESSAGESTATUS  dwStatus;
  RILMESSAGE        rmMessage;
} RILMESSAGEINFO, RILMESSAGEINFO;
````


## -struct-fields
<dl>

### -field cbSize

<dd></dd>

### -field hUiccApp

<dd></dd>

### -field dwParams

<dd></dd>

### -field dwIndex

<dd></dd>

### -field dwStatus

<dd></dd>

### -field rmMessage

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