---
UID: NF:printoem.OEMHalftonePattern
title: OEMHalftonePattern function
author: windows-driver-content
description: OEMHalftonePattern function
old-location: print\oemhalftonepattern.htm
old-project: print
ms.assetid: c574d997-736e-4883-a2c3-447985fcee55
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: OEMHalftonePattern, OEMHalftonePattern function [Print Devices], print.oemhalftonepattern, print_obsoletefunctions_5b15743c-f7ce-4107-a263-5cf28ead726d.xml, printoem/OEMHalftonePattern
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
req.lib: NtosKrnl.exe
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
-	OEMHalftonePattern
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMHalftonePattern function


## Syntax

````
BOOL APIENTRY OEMHalftonePattern(
       PDEVOBJ                                 pdevobj,
       PBYTE                                   pHTPattern,
       DWORD                                   dwHTPatternX,
       DWORD                                   dwHTPatternY,
       DWORD                                   dwHTNumPatterns,
       DWORD                                   dwCallbackID,
  _In_ _reads_bytes_opt_(dwResourceSize) PBYTE pResource,
       DWORD                                   dwResourceSize
);
````

## Parameters

`pdevobj`



`pHTPattern`



`dwHTPatternX`



`dwHTPatternY`



`dwHTNumPatterns`



`dwCallbackID`



`pResource`



`dwResourceSize`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |