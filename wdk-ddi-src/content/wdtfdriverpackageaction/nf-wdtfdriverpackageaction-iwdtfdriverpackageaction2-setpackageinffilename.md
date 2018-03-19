---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.SetPackageInfFileName
title: IWDTFDriverPackageAction2::SetPackageInfFileName method
author: windows-driver-content
description: Sets the pre-imported driver package path.
old-location: dtf\iwdtfdriverpackageaction2_setpackageinffilename.htm
old-project: dtf
ms.assetid: 68c2005e-c54b-413e-955a-864a05b23f4e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], SetPackageInfFileName method, IWDTFDriverPackageAction2::SetPackageInfFileName, Microsoft.WDTF.IWDTFDriverPackageAction2.SetPackageInfFileName, Microsoft::WDTF::IWDTFDriverPackageAction2::SetPackageInfFileName, SetPackageInfFileName method [Windows Device Testing Framework], SetPackageInfFileName method [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface, SetPackageInfFileName,IWDTFDriverPackageAction2.SetPackageInfFileName, dtf.iwdtfdriverpackageaction2_setpackageinffilename, wdtfdriverpackageaction/IWDTFDriverPackageAction2::SetPackageInfFileName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverPackageAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPackageAction.Interop.dll
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
-	WDTFDriverPackageAction.Interop.dll
api_name:
-	IWDTFDriverPackageAction2.SetPackageInfFileName
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# SetPackageInfFileName method
Sets the pre-imported driver package path.

## Syntax

````
HRESULT SetPackageInfFileName(
  [in] BSTR pDriverPackageInfFileName
);
````

## Parameters

`pDriverPackageInfFileName`

The driver package path.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfdriverpackageaction.h |

## See Also

<a href="..\wdtfdriverpackageaction\nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2.md">IWDTFDriverPackageAction2</a>