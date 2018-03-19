---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.ClearTriageLogs
title: IWDTFDriverSetupSystemAction2::ClearTriageLogs method
author: windows-driver-content
description: Clears the system device setup triage logs.
old-location: dtf\iwdtfdriversetupsystemaction2_cleartriagelogs.htm
old-project: dtf
ms.assetid: 5de5a7b9-4ac8-4d5a-8037-eec39a580372
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ClearTriageLogs method [Windows Device Testing Framework], ClearTriageLogs method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, ClearTriageLogs,IWDTFDriverSetupSystemAction2.ClearTriageLogs, IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], ClearTriageLogs method, IWDTFDriverSetupSystemAction2::ClearTriageLogs, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.ClearTriageLogs, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::ClearTriageLogs, dtf.iwdtfdriversetupsystemaction2_cleartriagelogs, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::ClearTriageLogs
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
-	IWDTFDriverSetupSystemAction2.ClearTriageLogs
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# ClearTriageLogs method
Clears the system device setup triage logs.

## Syntax

````
HRESULT ClearTriageLogs();
````

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtfdriversetupsystemaction.h |

## See Also

<a href="..\wdtfdriversetupsystemaction\nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md">IWDTFDriverSetupSystemAction2</a>