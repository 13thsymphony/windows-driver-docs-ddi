---
UID: NF:winddiui.DrvSplEndPage
title: DrvSplEndPage function
author: windows-driver-content
description: "."
old-location: print\drvsplendpage.htm
old-project: print
ms.assetid: 09c3db82-7890-48c8-a91f-3d1f3f01ef84
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: DrvSplEndPage function [Print Devices], print_interface-graphics_e5fbdcf3-d462-4ae9-8187-546a87189e19.xml, winddiui/DrvSplEndPage, DrvSplEndPage, print.drvsplendpage
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
-	DrvSplEndPage
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_VERSION, WINBIO_VERSION"
req.product: Windows 10 or later.
---


# DrvSplEndPage function


## Syntax

````
BOOL WINAPI DrvSplEndPage(
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