---
UID: NF:printoem.OEMEnableDriver
title: OEMEnableDriver function
author: windows-driver-content
description: OEMEnableDriver function
old-location: print\oemenabledriver.htm
old-project: print
ms.assetid: 9ea2f53c-de27-4803-b09a-444180b796ac
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMEnableDriver, OEMEnableDriver function [Print Devices], print.oemenabledriver, print_obsoletefunctions_4fe2a5f6-e5ad-4e35-b3d5-668e0cf96ee3.xml, printoem/OEMEnableDriver
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
-	OEMEnableDriver
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMEnableDriver function


## Syntax

````
DWORD APIENTRY OEMEnableDriver(
        DWORD                                 dwOemIntfVersion,
        DWORD                                 cbSize,
  _Out_ _writes_bytes_(cbSize) PDRVENABLEDATA pded
);
````

## Parameters

`dwOemIntfVersion`



`cbSize`



`pded`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |