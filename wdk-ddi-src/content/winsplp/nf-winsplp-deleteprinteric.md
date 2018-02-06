---
UID: NF:winsplp.DeletePrinterIC
title: DeletePrinterIC function
author: windows-driver-content
description: "."
old-location: print\deleteprinteric.htm
old-project: print
ms.assetid: 8D79AB9D-02BB-4032-AC5D-9099A672382F
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: DeletePrinterIC function [Print Devices], DeletePrinterIC, print.deleteprinteric, winsplp/DeletePrinterIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
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
-	Winsplp.h
apiname:
-	DeletePrinterIC
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# DeletePrinterIC function


## Syntax

````
BOOL WINAPI DeletePrinterIC(
  _In_ HANDLE hPrinterIC
);
````

## Parameters

`hPrinterIC`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |