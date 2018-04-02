---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.RemoveDriverPackage
title: IWDTFDriverSetupSystemAction2::RemoveDriverPackage method
author: windows-driver-content
description: Removes a driver package from the driver store.
old-location: dtf\iwdtfdriversetupsystemaction2_removedriverpackage.htm
old-project: dtf
ms.assetid: de742d86-d38c-4d33-b808-678b5cb7419e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], RemoveDriverPackage method, IWDTFDriverSetupSystemAction2::RemoveDriverPackage, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.RemoveDriverPackage, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::RemoveDriverPackage, RemoveDriverPackage method [Windows Device Testing Framework], RemoveDriverPackage method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, RemoveDriverPackage,IWDTFDriverSetupSystemAction2.RemoveDriverPackage, dtf.iwdtfdriversetupsystemaction2_removedriverpackage, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::RemoveDriverPackage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriversetupsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupSystemAction.Interop.dll
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
-	WDTFDriverSetupSystemAction.Interop.dll
api_name:
-	IWDTFDriverSetupSystemAction2.RemoveDriverPackage
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFDriverSetupSystemAction2::RemoveDriverPackage method
Removes a driver package from the driver store.

## Syntax

```
HRESULT RemoveDriverPackage(
  IWDTFDriverPackageAction2 *pDp
);
```

## Parameters

`pDp`

The driver package to remove.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfdriversetupsystemaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450948">IWDTFDriverSetupSystemAction2</a>