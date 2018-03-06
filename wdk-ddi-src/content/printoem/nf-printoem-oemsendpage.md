---
UID: NF:printoem.OEMSendPage
title: OEMSendPage function
author: windows-driver-content
description: The OEMSendPage function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.
old-location: print\oemsendpage.htm
old-project: print
ms.assetid: 9a3380d0-2d90-49ec-b97d-be55eb6eaaa5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMSendPage, OEMSendPage function [Print Devices], print.oemsendpage, print_unidrv-pscript_rendering_6a896dea-57aa-4fa0-810f-dadb79b13079.xml, printoem/OEMSendPage
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
-	OEMSendPage
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMSendPage function
The <code>OEMSendPage</code> function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.

## Syntax

````
BOOL APIENTRY OEMSendPage(
   SURFOBJ *pso
);
````

## Parameters

`pso`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |