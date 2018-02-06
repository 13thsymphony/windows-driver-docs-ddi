---
UID: NS:ntddrilapitypes.RILSETUICCLOCKENABLEDPARAMS
title: RILSETUICCLOCKENABLEDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetuicclockenabledparams.htm
old-project: netvista
ms.assetid: 03df5865-a383-447b-8e80-671ba7a3a60e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSETUICCLOCKENABLEDPARAMS, RILSETUICCLOCKENABLEDPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetuicclockenabledparams, ntddrilapitypes/RILSETUICCLOCKENABLEDPARAMS, *LPRILSETUICCLOCKENABLEDPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILSETUICCLOCKENABLEDPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETUICCLOCKENABLEDPARAMS, RILSETUICCLOCKENABLEDPARAMS"
---

# RILSETUICCLOCKENABLEDPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSETUICCLOCKENABLEDPARAMS {
  RILUICCLOCKCREDENTIAL  lockCredential;
  BOOL                   fEnable;
} RILSETUICCLOCKENABLEDPARAMS, RILSETUICCLOCKENABLEDPARAMS;
````

## Members


`fEnable`



`lockCredential`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |