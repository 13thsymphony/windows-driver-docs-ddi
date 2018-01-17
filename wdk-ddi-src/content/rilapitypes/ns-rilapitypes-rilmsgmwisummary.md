---
UID: NS:rilapitypes.RILMSGMWISUMMARY
title: RILMSGMWISUMMARY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummary_2.htm
old-project: netvista
ms.assetid: 809373c0-210e-4947-a92f-a945b7846da7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILMSGMWISUMMARY, *LPRILMSGMWISUMMARY, RILMSGMWISUMMARY
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
req.alt-api: RILMSGMWISUMMARY
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILMSGMWISUMMARY, RILMSGMWISUMMARY
req.product: Windows 10 or later.
---

# RILMSGMWISUMMARY structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILMSGMWISUMMARY {
  RILMSGMWITYPE  dwMwiType;
  DWORD          dwNumberOfNewMessages;
  DWORD          dwNumberOfOldMessages;
  DWORD          dwNumberOfNewUrgentMessages;
  DWORD          dwNumberOfOldUrgentMessages;
} RILMSGMWISUMMARY, RILMSGMWISUMMARY;
````


## -struct-fields

### -field dwMwiType


### -field dwNumberOfNewMessages


### -field dwNumberOfOldMessages


### -field dwNumberOfNewUrgentMessages


### -field dwNumberOfOldUrgentMessages


## -remarks
