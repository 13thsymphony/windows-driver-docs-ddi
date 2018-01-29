---
UID : NS:nfcsedev._SECURE_ELEMENT_TECH_ROUTING_INFO
title : _SECURE_ELEMENT_TECH_ROUTING_INFO
author : windows-driver-content
description : SECURE_ELEMENT_TECH_ROUTING_INFO is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location : nfpdrivers\_secure_element_tech_routing_info.htm
old-project : nfpdrivers
ms.assetid : 62622A56-D84A-40E4-9CFA-4B0938B8FD85
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : nfcsedev/_SECURE_ELEMENT_TECH_ROUTING_INFO, P_SECURE_ELEMENT_TECH_ROUTING_INFO structure pointer [Near-Field Proximity Drivers], SECURE_ELEMENT_TECH_ROUTING_INFO structure [Near-Field Proximity Drivers], _SECURE_ELEMENT_TECH_ROUTING_INFO, *PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO, P_SECURE_ELEMENT_TECH_ROUTING_INFO, nfcsedev/P_SECURE_ELEMENT_TECH_ROUTING_INFO, nfpdrivers._secure_element_tech_routing_info
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : nfcsedev.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSECURE_ELEMENT_TECH_ROUTING_INFO, SECURE_ELEMENT_TECH_ROUTING_INFO"
---

# _SECURE_ELEMENT_TECH_ROUTING_INFO structure
SECURE_ELEMENT_TECH_ROUTING_INFO is  a member of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_routing_table_entry.md">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.

## Syntax
````
typedef struct _SECURE_ELEMENT_TECH_ROUTING_INFO {
  GUID guidSecureElementId;
  BYTE eRfTechType;
} SECURE_ELEMENT_TECH_ROUTING_INFO, *P_SECURE_ELEMENT_TECH_ROUTING_INFO;
````

## Members


`eRfTechType`

NFC Forum RF technology type.

`guidSecureElementId`

Secure element unique identifier returned by enumeration DDI.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | nfcsedev.h |