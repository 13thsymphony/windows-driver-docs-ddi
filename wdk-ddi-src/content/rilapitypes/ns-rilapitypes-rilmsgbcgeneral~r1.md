---
UID: NS.rilapitypes.RILMSGBCGENERAL~r1
title: RILMSGBCGENERAL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgbcgeneral_2.htm
old-project: netvista
ms.assetid: 7202683f-5e02-48dd-b8b7-cb998fd660df
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RILMSGBCGENERAL,
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
req.alt-api: RILMSGBCGENERAL
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

# RILMSGBCGENERAL structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILMSGBCGENERAL {
  RILGEOSCOPE                       dwGeoScope;
  DWORD                             dwMsgCode;
  DWORD                             dwUpdateNumber;
  DWORD                             dwID;
  DWORD                             dwSerialNumber;
  RILMSGDCS                         rmdDataCoding;
  DWORD                             dwTotalPages;
  DWORD                             dwPageNumber;
  RILMSGBCGENERALWARNINGTYPE        dwWarningType;
  BOOL                              bEmergencyUserAlert;
  BOOL                              bMessagePopup;
  RILSYSTEMTIME                     stSCReceiveTime;
  BYTE [MAXLENGTH_DIGITALSIGNATURE] digSig;
  DWORD                             cchMsgLength;
  BYTE [MAXLENGTH_MSG]              rgbMsg;
} RILMSGBCGENERAL, RILMSGBCGENERAL;
````


## -struct-fields
<dl>

### -field <b>dwGeoScope</b>

<dd></dd>

### -field <b>dwMsgCode</b>

<dd></dd>

### -field <b>dwUpdateNumber</b>

<dd></dd>

### -field <b>dwID</b>

<dd></dd>

### -field <b>dwSerialNumber</b>

<dd></dd>

### -field <b>rmdDataCoding</b>

<dd></dd>

### -field <b>dwTotalPages</b>

<dd></dd>

### -field <b>dwPageNumber</b>

<dd></dd>

### -field <b>dwWarningType</b>

<dd></dd>

### -field <b>bEmergencyUserAlert</b>

<dd></dd>

### -field <b>bMessagePopup</b>

<dd></dd>

### -field <b>stSCReceiveTime</b>

<dd></dd>

### -field <b>digSig</b>

<dd></dd>

### -field <b>cchMsgLength</b>

<dd></dd>

### -field <b>rgbMsg</b>

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