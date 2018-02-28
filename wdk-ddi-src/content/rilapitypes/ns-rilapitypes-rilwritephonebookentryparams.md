---
UID: NS:rilapitypes.RILWRITEPHONEBOOKENTRYPARAMS
title: RILWRITEPHONEBOOKENTRYPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilwritephonebookentryparams_2.htm
old-project: netvista
ms.assetid: ae92f321-d6dc-4e48-8107-1a6fbd3bb15a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilwritephonebookentryparams_2, rilapitypes/RILWRITEPHONEBOOKENTRYPARAMS"
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
-	rilapitypes.h
api_name:
-	RILWRITEPHONEBOOKENTRYPARAMS
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RILWRITEPHONEBOOKENTRYPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILWRITEPHONEBOOKENTRYPARAMS {
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
  BOOL                        fHasLockVerification;
  RILUICCLOCKCREDENTIAL       lockVerification;
  RILPHONEBOOKENTRY           pbEntry;
} RILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS;
````

## Members


`dwStoreLocation`



`fHasLockVerification`



`hUiccApp`



`lockVerification`



`pbEntry`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |