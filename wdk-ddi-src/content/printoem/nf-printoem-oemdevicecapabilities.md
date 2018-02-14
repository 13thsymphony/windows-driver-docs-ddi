---
UID: NF:printoem.OEMDeviceCapabilities
title: OEMDeviceCapabilities function
author: windows-driver-content
description: OEMDeviceCapabilities function
old-location: print\oemdevicecapabilities.htm
old-project: print
ms.assetid: fb15fd82-6214-40c0-9982-faee6c6b35b3
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMDeviceCapabilities, print_obsoletefunctions_7ab2cfd8-e7cd-4f7c-be2d-a53dbb3651c9.xml, print.oemdevicecapabilities, OEMDeviceCapabilities function [Print Devices], printoem/OEMDeviceCapabilities
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMDeviceCapabilities
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMDeviceCapabilities function


## Syntax

````
DWORD APIENTRY OEMDeviceCapabilities(
   POEMUIOBJ poemuiobj,
   HANDLE    hPrinter,
   PWSTR     pDeviceName,
   WORD      wCapability,
   PVOID     pOutput,
   PDEVMODE  pPublicDM,
   PVOID     pOEMDM,
   DWORD     dwLastResult
);
````

## Parameters

`poemuiobj`



`hPrinter`



`pDeviceName`



`wCapability`



`pOutput`



`pPublicDM`



`pOEMDM`



`dwLastResult`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |