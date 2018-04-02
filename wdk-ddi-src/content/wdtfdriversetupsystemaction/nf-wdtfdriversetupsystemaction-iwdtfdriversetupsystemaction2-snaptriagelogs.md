---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.SnapTriageLogs
title: IWDTFDriverSetupSystemAction2::SnapTriageLogs method
author: windows-driver-content
description: Copies the driver setup triage logs.
old-location: dtf\iwdtfdriversetupsystemaction2_snaptriagelogs.htm
old-project: dtf
ms.assetid: 52f1e529-e1fe-4a08-a0cf-dc08e18d11b5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], SnapTriageLogs method, IWDTFDriverSetupSystemAction2::SnapTriageLogs, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.SnapTriageLogs, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::SnapTriageLogs, SnapTriageLogs method [Windows Device Testing Framework], SnapTriageLogs method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, SnapTriageLogs,IWDTFDriverSetupSystemAction2.SnapTriageLogs, dtf.iwdtfdriversetupsystemaction2_snaptriagelogs, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::SnapTriageLogs
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
-	IWDTFDriverSetupSystemAction2.SnapTriageLogs
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFDriverSetupSystemAction2::SnapTriageLogs method
Copies the driver setup triage logs.

## Syntax

```
HRESULT SnapTriageLogs(

);
```

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

The <b>SnapTriageLogs</b> method copies the current driver setup 
triage logs to the current directory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfdriversetupsystemaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450948">IWDTFDriverSetupSystemAction2</a>