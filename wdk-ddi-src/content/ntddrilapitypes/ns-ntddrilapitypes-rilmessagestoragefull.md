---
UID: NS:ntddrilapitypes.RILMESSAGESTORAGEFULL
title: RILMESSAGESTORAGEFULL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagestoragefull.htm
old-project: netvista
ms.assetid: 3369feeb-cbb9-4938-8dfd-0160ba4fefdf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMESSAGESTORAGEFULL, *LPRILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL
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
req.alt-api: RILMESSAGESTORAGEFULL
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
req.typenames: *LPRILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL
---

# RILMESSAGESTORAGEFULL structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMESSAGESTORAGEFULL {
  DWORD     cbSize;
  DWORD     dwExecutor;
  HUICCAPP  hUiccApp;
} RILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field hUiccApp


## -remarks
