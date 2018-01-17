---
UID: NS:ntddrilapitypes.RILGETOPERATORLISTPARAMS
title: RILGETOPERATORLISTPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetoperatorlistparams.htm
old-project: netvista
ms.assetid: 75c8b3b3-4f33-465a-a35c-9d3056a2eb75
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETOPERATORLISTPARAMS, *LPRILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS
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
req.alt-api: RILGETOPERATORLISTPARAMS
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
req.typenames: *LPRILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS
---

# RILGETOPERATORLISTPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILGETOPERATORLISTPARAMS {
  DWORD  dwExecutor;
  DWORD  dwSystemTypes;
} RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwSystemTypes


## -remarks
