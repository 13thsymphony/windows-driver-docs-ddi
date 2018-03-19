---
UID: NF:prcomoem.IPrintOemEngine.ResetPDEV
title: IPrintOemEngine::ResetPDEV method
author: windows-driver-content
description: "."
old-location: print\iprintoemengine_resetpdev.htm
old-project: print
ms.assetid: DD8E4DAC-A4CA-4F1A-A898-E4A68A2D6715
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemEngine, IPrintOemEngine interface [Print Devices], ResetPDEV method, IPrintOemEngine::ResetPDEV, ResetPDEV method [Print Devices], ResetPDEV method [Print Devices], IPrintOemEngine interface, ResetPDEV,IPrintOemEngine.ResetPDEV, prcomoem/IPrintOemEngine::ResetPDEV, print.iprintoemengine_resetpdev
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
-	IPrintOemEngine.ResetPDEV
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# ResetPDEV method


## Syntax

````
HRESULT ResetPDEV(
   PDEVOBJ pdevobjOld,
   PDEVOBJ pdevobjNew
);
````

## Parameters

`pdevobjOld`



`pdevobjNew`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintoemengine.md">IPrintOemEngine</a>