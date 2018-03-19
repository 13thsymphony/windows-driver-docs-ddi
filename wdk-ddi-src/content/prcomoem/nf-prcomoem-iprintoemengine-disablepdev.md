---
UID: NF:prcomoem.IPrintOemEngine.DisablePDEV
title: IPrintOemEngine::DisablePDEV method
author: windows-driver-content
description: "."
old-location: print\iprintoemengine_disablepdev.htm
old-project: print
ms.assetid: F550A8B8-0C96-46E8-8E2A-32679E1D1E01
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DisablePDEV method [Print Devices], DisablePDEV method [Print Devices], IPrintOemEngine interface, DisablePDEV,IPrintOemEngine.DisablePDEV, IPrintOemEngine, IPrintOemEngine interface [Print Devices], DisablePDEV method, IPrintOemEngine::DisablePDEV, prcomoem/IPrintOemEngine::DisablePDEV, print.iprintoemengine_disablepdev
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
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
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintOemEngine.DisablePDEV
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# DisablePDEV method


## Syntax

````
HRESULT DisablePDEV(
   PDEVOBJ pdevobj
);
````

## Parameters

`pdevobj`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintoemengine.md">IPrintOemEngine</a>