---
UID: NF:prcomoem.IPrintOemEngine.EnablePDEV
title: IPrintOemEngine::EnablePDEV method
author: windows-driver-content
description: "."
old-location: print\iprintoemengine_enablepdev.htm
old-project: print
ms.assetid: F84B7A8F-5B75-4E2F-93EB-AFFE24637647
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EnablePDEV method [Print Devices], EnablePDEV method [Print Devices], IPrintOemEngine interface, EnablePDEV,IPrintOemEngine.EnablePDEV, IPrintOemEngine, IPrintOemEngine interface [Print Devices], EnablePDEV method, IPrintOemEngine::EnablePDEV, prcomoem/IPrintOemEngine::EnablePDEV, print.iprintoemengine_enablepdev
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
-	IPrintOemEngine.EnablePDEV
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# EnablePDEV method


## Syntax

````
HRESULT EnablePDEV(
   PDEVOBJ       pdevobj,
   PWSTR         pPrinterName,
   ULONG         cPatterns,
   HSURF         *phsurfPatterns,
   ULONG         cjGdiInfo,
   GDIINFO       *pGdiInfo,
   ULONG         cjDevInfo,
   DEVINFO       *pDevInfo,
   DRVENABLEDATA *pded,
   PDEVOEM       *pDevOem
);
````

## Parameters

`pdevobj`



`pPrinterName`



`cPatterns`



`phsurfPatterns`



`cjGdiInfo`



`pGdiInfo`



`cjDevInfo`



`pDevInfo`



`pded`



`pDevOem`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintoemengine.md">IPrintOemEngine</a>