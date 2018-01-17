---
UID: NS:ntddrilapitypes.RILGETPHONEBOOKOPTIONSPARAMS
title: RILGETPHONEBOOKOPTIONSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetphonebookoptionsparams.htm
old-project: netvista
ms.assetid: a6c71f2d-baf7-4293-ae13-38625be3ab3f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETPHONEBOOKOPTIONSPARAMS, *LPRILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS
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
req.alt-api: RILGETPHONEBOOKOPTIONSPARAMS
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS
---

# RILGETPHONEBOOKOPTIONSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILGETPHONEBOOKOPTIONSPARAMS {
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
} RILGETPHONEBOOKOPTIONSPARAMS, RILGETPHONEBOOKOPTIONSPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field dwStoreLocation


## -remarks
