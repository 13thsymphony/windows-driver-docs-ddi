---
UID: NS:ntddrilapitypes.RILPHONEBOOKADDITIONALNUMBERSTRING
title: RILPHONEBOOKADDITIONALNUMBERSTRING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberstring.htm
old-project: netvista
ms.assetid: 1d201c4d-606d-4461-ad3d-df48d3455724
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILPHONEBOOKADDITIONALNUMBERSTRING, netvista.rilphonebookadditionalnumberstring, ntddrilapitypes/RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING structure [Network Drivers Starting with Windows Vista]"
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
-	RILPHONEBOOKADDITIONALNUMBERSTRING
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKADDITIONALNUMBERSTRING, *LPRILPHONEBOOKADDITIONALNUMBERSTRING
---

# RILPHONEBOOKADDITIONALNUMBERSTRING structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKADDITIONALNUMBERSTRING {
  DWORD       cbSize;
  DWORD       dwNumId;
  WCHAR [256] wszText;
} RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING;
````

## Members


`cbSize`



`dwNumId`



`wszText`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |