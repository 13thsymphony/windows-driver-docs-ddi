---
UID: NF:printoem.OEMTTYGetInfo
title: OEMTTYGetInfo function
author: windows-driver-content
description: OEMTTYGetInfo function
old-location: print\oemttygetinfo.htm
old-project: print
ms.assetid: 9b6fcd4e-6472-4e46-b0b7-dd1279e534d0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMTTYGetInfo, OEMTTYGetInfo function [Print Devices], print.oemttygetinfo, print_obsoletefunctions_7da21ed3-626e-454f-9357-0ab0a0640a27.xml, printoem/OEMTTYGetInfo
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
-	OEMTTYGetInfo
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMTTYGetInfo function


## Syntax

````
INT APIENTRY OEMTTYGetInfo(
        PDEVOBJ                      pdevobj,
        DWORD                        dwInfoIndex,
  _Out_ _writes_bytes_(dwSize) PVOID pOutputBuf,
        DWORD                        dwSize,
  _Out_ DWORD                        *pcbcNeeded
);
````

## Parameters

`pdevobj`



`dwInfoIndex`



`pOutputBuf`



`dwSize`



`pcbcNeeded`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |