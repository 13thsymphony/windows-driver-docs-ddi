---
UID: NS:pointofservicedriverinterface._MSR_UPDATE_KEY
title: "_MSR_UPDATE_KEY"
author: windows-driver-content
description: This structure contains the information necessary to set a new encryption key.
old-location: pos\msr_update_key.htm
old-project: pos
ms.assetid: 8d7f85d4-af10-4ae5-a891-18dd41192c6a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: MSR_UPDATE_KEY structure, PMSR_UPDATE_KEY structure pointer, *PMSR_UPDATE_KEY, PMSR_UPDATE_KEY, pointofservicedriverinterface/MSR_UPDATE_KEY, _MSR_UPDATE_KEY, pos.msr_update_key, MSR_UPDATE_KEY, pointofservicedriverinterface/PMSR_UPDATE_KEY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
apiname:
-	MSR_UPDATE_KEY
product: Windows
targetos: Windows
req.typenames: "*PMSR_UPDATE_KEY, MSR_UPDATE_KEY"
---

# _MSR_UPDATE_KEY structure
This structure contains the information necessary to set a new encryption key.

## Syntax
````
typedef struct _MSR_UPDATE_KEY {
  unsigned char KeyLength;
  unsigned char KeyNameLength;
  unsigned char Key[MSR_KEY_SIZE];
  unsigned char char KeyName[MSR_KEY_NAME_SIZE];
} MSR_UPDATE_KEY, *PMSR_UPDATE_KEY;
````

## Members


`Key`

The new encryption key.

`KeyLength`

Length, in bytes, of the key stored in <b>Key[MSR_KEY_SIZE]</b>.

`KeyName`



`KeyNameLength`

Length, in bytes, of the key name stored in <b>KeyName[MSR_KEY_SIZE]</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |