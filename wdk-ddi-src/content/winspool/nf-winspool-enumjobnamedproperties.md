---
UID: NF:winspool.EnumJobNamedProperties
title: EnumJobNamedProperties function
author: windows-driver-content
description: "."
old-location: print\enumjobnamedproperties.htm
old-project: print
ms.assetid: 0C5E2279-79D0-40A2-BA5B-66994A22E963
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EnumJobNamedProperties, EnumJobNamedProperties function [Print Devices], print.enumjobnamedproperties, winspool/EnumJobNamedProperties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
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
-	Winspool.h
api_name:
-	EnumJobNamedProperties
product:
- Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---


# EnumJobNamedProperties function


## Syntax

```
DWORD EnumJobNamedProperties(
  HANDLE             hPrinter,
  DWORD              JobId,
  DWORD              *pcProperties,
  PrintNamedProperty **ppProperties
);
```

## Parameters

`hPrinter`



`JobId`



`pcProperties`



`ppProperties`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winspool.h |