---
UID: NS.NFCSEDEV._SECURE_ELEMENT_PROTO_ROUTING_INFO
title: _SECURE_ELEMENT_PROTO_ROUTING_INFO
author: windows-driver-content
description: SECURE_ELEMENT_PROTO_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_proto_routing_info.htm
old-project: nfpdrivers
ms.assetid: E22C5985-13A8-4A55-A97B-DABD7E475BD3
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_PROTO_ROUTING_INFO, *PSECURE_ELEMENT_PROTO_ROUTING_INFO, SECURE_ELEMENT_PROTO_ROUTING_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECURE_ELEMENT_PROTO_ROUTING_INFO
req.alt-loc: nfcsedev.h
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
---

# _SECURE_ELEMENT_PROTO_ROUTING_INFO structure



## -description
SECURE_ELEMENT_PROTO_ROUTING_INFO
 is a member of <a href="nfpdrivers._secure_element_routing_table_entry">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>. 


## -syntax

````
typedef struct _SECURE_ELEMENT_PROTO_ROUTING_INFO {
  GUID guidSecureElementId;
  BYTE eRfProtocolType;
} SECURE_ELEMENT_PROTO_ROUTING_INFO, *P_SECURE_ELEMENT_PROTO_ROUTING_INFO;
````


## -struct-fields

### -field guidSecureElementId

Secure element unique identifier returned by enumeration DDI.

### -field eRfProtocolType

NFC Forum RF protocol.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Nfcsedev.h</dt>
</dl>
</td>
</tr>
</table>