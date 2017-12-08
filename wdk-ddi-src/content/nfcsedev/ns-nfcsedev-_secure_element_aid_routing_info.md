---
UID: NS.NFCSEDEV._SECURE_ELEMENT_AID_ROUTING_INFO
title: _SECURE_ELEMENT_AID_ROUTING_INFO
author: windows-driver-content
description: SECURE_ELEMENT_AID_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_aid_routing_info.htm
old-project: nfpdrivers
ms.assetid: 3F9831D1-68A9-4FDB-93C6-6983E6BFE945
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_AID_ROUTING_INFO, SECURE_ELEMENT_AID_ROUTING_INFO, *PSECURE_ELEMENT_AID_ROUTING_INFO
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
req.alt-api: SECURE_ELEMENT_AID_ROUTING_INFO
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

# _SECURE_ELEMENT_AID_ROUTING_INFO structure



## -description
SECURE_ELEMENT_AID_ROUTING_INFO is a member of <a href="nfpdrivers._secure_element_routing_table_entry">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.


## -syntax

````
typedef struct _SECURE_ELEMENT_AID_ROUTING_INFO {
  GUID                                                   guidSecureElementId;
   _Field_range_(<= , ISO_7816_MAXIMUM_AID_LENGTH) DWORD cbAid;
   _Field_size_bytes_(cbAid) BYTE                        pbAid[16];
} SECURE_ELEMENT_AID_ROUTING_INFO, *P_SECURE_ELEMENT_AID_ROUTING_INFO;
````


## -struct-fields

### -field guidSecureElementId

Secure element unique identifier returned by enumeration DDI.



### -field cbAid

Length of applet ID buffer.

### -field pbAid[16]

Buffer holding ISO 7816 AID.

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