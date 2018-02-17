---
UID: NS:nfcsedev._SECURE_ELEMENT_ENDPOINT_INFO
title: "_SECURE_ELEMENT_ENDPOINT_INFO"
author: windows-driver-content
description: SECURE_ELEMENT_ENDPOINT_INFO is a member of SECURE_ELEMENT_ENDPOINT_LIST.
old-location: nfpdrivers\_secure_element_endpoint_info.htm
old-project: nfpdrivers
ms.assetid: C1D812BD-55F0-44F7-BCC8-81CC758EDEF3
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfcsedev/_SECURE_ELEMENT_ENDPOINT_INFO, nfpdrivers._secure_element_endpoint_info, SECURE_ELEMENT_ENDPOINT_INFO structure [Near-Field Proximity Drivers], P_SECURE_ELEMENT_ENDPOINT_INFO structure pointer [Near-Field Proximity Drivers], nfcsedev/P_SECURE_ELEMENT_ENDPOINT_INFO, *PSECURE_ELEMENT_ENDPOINT_INFO, SECURE_ELEMENT_ENDPOINT_INFO, P_SECURE_ELEMENT_ENDPOINT_INFO, _SECURE_ELEMENT_ENDPOINT_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcsedev.h
apiname:
-	SECURE_ELEMENT_ENDPOINT_INFO
product: Windows
targetos: Windows
req.typenames: SECURE_ELEMENT_ENDPOINT_INFO, *PSECURE_ELEMENT_ENDPOINT_INFO
---

# _SECURE_ELEMENT_ENDPOINT_INFO structure
SECURE_ELEMENT_ENDPOINT_INFO is a member of <a href="..\nfcsedev\ns-nfcsedev-_secure_element_endpoint_list.md">SECURE_ELEMENT_ENDPOINT_LIST</a>.

## Syntax
````
typedef struct _SECURE_ELEMENT_ENDPOINT_INFO {
  GUID                guidSecureElementId;
  SECURE_ELEMENT_TYPE eSecureElementType;
} SECURE_ELEMENT_ENDPOINT_INFO, *P_SECURE_ELEMENT_ENDPOINT_INFO;
````

## Members


`eSecureElementType`

Type of secure element endpoint (NFCEE).

`guidSecureElementId`

This is a unique identifier for the secure element.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |