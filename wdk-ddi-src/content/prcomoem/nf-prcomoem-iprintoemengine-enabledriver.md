---
UID: NF:prcomoem.IPrintOemEngine.EnableDriver
title: IPrintOemEngine::EnableDriver method
author: windows-driver-content
description: "."
old-location: print\iprintoemengine_enabledriver.htm
old-project: print
ms.assetid: 638E4FBE-8F53-4509-BFAE-59C02D2D1C4B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EnableDriver method [Print Devices], EnableDriver method [Print Devices], IPrintOemEngine interface, EnableDriver,IPrintOemEngine.EnableDriver, IPrintOemEngine, IPrintOemEngine interface [Print Devices], EnableDriver method, IPrintOemEngine::EnableDriver, prcomoem/IPrintOemEngine::EnableDriver, print.iprintoemengine_enabledriver
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
-	IPrintOemEngine.EnableDriver
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# EnableDriver method


## Syntax

````
HRESULT EnableDriver(
   DWORD          DriverVersion,
   DWORD          cbSize,
   PDRVENABLEDATA pded
);
````

## Parameters

`DriverVersion`



`cbSize`



`pded`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintoemengine.md">IPrintOemEngine</a>