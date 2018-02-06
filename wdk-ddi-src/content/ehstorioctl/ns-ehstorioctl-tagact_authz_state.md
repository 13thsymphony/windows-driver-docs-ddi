---
UID: NS:ehstorioctl.tagACT_AUTHZ_STATE
title: tagACT_AUTHZ_STATE
author: windows-driver-content
description: This structure describes the Addressable Command Target (ACT) authorization state.
old-location: storage\act_authz_state.htm
old-project: storage
ms.assetid: 32bb774f-b1eb-4198-8e4c-febcac83153d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PACT_AUTHZ_STATE, ehstorioctl/PACT_AUTHZ_STATE, PACT_AUTHZ_STATE, tagACT_AUTHZ_STATE, structs-silo_5a83edfd-d997-4f63-bbb9-58ec7cab438f.xml, ehstorioctl/ACT_AUTHZ_STATE, ACT_AUTHZ_STATE, storage.act_authz_state, ACT_AUTHZ_STATE structure [Storage Devices], PACT_AUTHZ_STATE structure pointer [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
-	EhStorIoctl.h
apiname:
-	ACT_AUTHZ_STATE
product: Windows
targetos: Windows
req.typenames: ACT_AUTHZ_STATE, *PACT_AUTHZ_STATE
---

# tagACT_AUTHZ_STATE structure
This structure describes the Addressable Command Target (ACT) authorization state.

## Syntax
````
typedef struct tagACT_AUTHZ_STATE {
  UCHAR   ACT;
  BOOLEAN fAuthorized;
} ACT_AUTHZ_STATE, *PACT_AUTHZ_STATE;
````

## Members


`ACT`

This member is ignored.

`fAuthorized`

This member may be either <b>TRUE</b> (authorized) or <b>FALSE</b> (not authorized).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |