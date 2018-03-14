---
UID: NS:rilapitypes.RILPHONEBOOKADDITIONALNUMBERINFO
title: RILPHONEBOOKADDITIONALNUMBERINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberinfo.htm
old-project: netvista
ms.assetid: bc4026e5-6613-4787-9218-22d1d3e447c3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO structure [Network Drivers Starting with Windows Vista], netvista.rilphonebookadditionalnumberinfo, ntddrilapitypes/RILPHONEBOOKADDITIONALNUMBERINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILPHONEBOOKADDITIONALNUMBERINFO
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKADDITIONALNUMBERINFO, *LPRILPHONEBOOKADDITIONALNUMBERINFO
req.product: Windows 10 or later.
---

# RILPHONEBOOKADDITIONALNUMBERINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKADDITIONALNUMBERINFO {
  DWORD                                  cbSize;
  DWORD                                  dwRilPBANSSize;
  RILPHONEBOOKADDITIONALNUMBERSTRING [1] RilPBANS;
} RILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO;
````

## Members


`cbSize`



`dwRilPBANSSize`



`RilPBANS`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |