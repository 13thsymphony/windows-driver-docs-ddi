---
UID: NS:winspool.PrintNamedProperty
title: PrintNamedProperty
author: windows-driver-content
description: "."
old-location: print\printnamedproperty.htm
old-project: print
ms.assetid: F7692594-DE13-4242-926C-F2706FF95E77
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PrintNamedProperty, PrintNamedProperty structure [Print Devices], print.printnamedproperty, winspool/PrintNamedProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	PrintNamedProperty
product: Windows
targetos: Windows
req.typenames: PrintNamedProperty
req.product: Windows 10 or later.
---

# PrintNamedProperty structure


## Syntax
````
typedef struct {
  WCHAR                    *propertyName;
  PrintPropertyValue       propertyValue;
} PrintNamedProperty;
````

## Members


`propertyName`



`propertyValue`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | winspool.h |