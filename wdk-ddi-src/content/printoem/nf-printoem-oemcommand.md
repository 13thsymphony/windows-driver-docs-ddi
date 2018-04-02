---
UID: NF:printoem.OEMCommand
title: OEMCommand function
author: windows-driver-content
description: OEMCommand function
old-location: print\oemcommand.htm
old-project: print
ms.assetid: 67f75696-dee4-43ec-90fd-96fd1a91ec16
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMCommand, OEMCommand function [Print Devices], print.oemcommand, print_obsoletefunctions_f6d1a0f9-6560-4e4c-9826-c2714b7c1ad3.xml, printoem/OEMCommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
api_name:
-	OEMCommand
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMCommand function


## Syntax

```
DWORD OEMCommand(
  PDEVOBJ pdevobj,
  DWORD   dwIndex,
  PVOID   pData,
  DWORD   cbSize
);
```

## Parameters

`pdevobj`



`dwIndex`



`pData`



`cbSize`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |