---
UID: NF:winddiui.DrvSplStartPage
title: DrvSplStartPage function
author: windows-driver-content
description: "."
old-location: print\drvsplstartpage.htm
old-project: print
ms.assetid: 7291a0ec-7a43-4fc6-ac1d-60487b2ad3d8
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: winddiui/DrvSplStartPage, print.drvsplstartpage, DrvSplStartPage function [Print Devices], DrvSplStartPage, print_interface-graphics_4f9a41e8-8706-428e-8f58-945485151f62.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winddiui.h
apiname:
-	DrvSplStartPage
product: Windows
targetos: Windows
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---


# DrvSplStartPage function


## Syntax

````
BOOL WINAPI DrvSplStartPage(
   HANDLE hDriver
);
````

## Parameters

`hDriver`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winddiui.h |
| **Library** | NtosKrnl.exe |