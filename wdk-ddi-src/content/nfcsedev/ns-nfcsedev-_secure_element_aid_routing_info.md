---
UID: NS:nfcsedev._SECURE_ELEMENT_AID_ROUTING_INFO
title: "_SECURE_ELEMENT_AID_ROUTING_INFO"
author: windows-driver-content
description: SECURE_ELEMENT_AID_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_aid_routing_info.htm
old-project: nfpdrivers
ms.assetid: 3F9831D1-68A9-4FDB-93C6-6983E6BFE945
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSECURE_ELEMENT_AID_ROUTING_INFO, P_SECURE_ELEMENT_AID_ROUTING_INFO, P_SECURE_ELEMENT_AID_ROUTING_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_AID_ROUTING_INFO, SECURE_ELEMENT_AID_ROUTING_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_AID_ROUTING_INFO, nfcsedev/P_SECURE_ELEMENT_AID_ROUTING_INFO, nfcsedev/_SECURE_ELEMENT_AID_ROUTING_INFO, nfpdrivers._secure_element_aid_routing_info"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfcsedev.h
api_name:
-	SECURE_ELEMENT_AID_ROUTING_INFO
product:
- Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_AID_ROUTING_INFO, *PSECURE_ELEMENT_AID_ROUTING_INFO
---

# _SECURE_ELEMENT_AID_ROUTING_INFO structure
SECURE_ELEMENT_AID_ROUTING_INFO is a member of <a href="https://msdn.microsoft.com/library/windows/hardware/dn905628">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.

## Syntax
```
typedef struct _SECURE_ELEMENT_AID_ROUTING_INFO {
  GUID  guidSecureElementId;
  DWORD cbAid;
  BYTE  pbAid[ISO_7816_MAXIMUM_AID_LENGTH];
} *PSECURE_ELEMENT_AID_ROUTING_INFO, SECURE_ELEMENT_AID_ROUTING_INFO;
```

## Members


`guidSecureElementId`

Secure element unique identifier returned by enumeration DDI.

`cbAid`

Length of applet ID buffer.

`pbAid`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |