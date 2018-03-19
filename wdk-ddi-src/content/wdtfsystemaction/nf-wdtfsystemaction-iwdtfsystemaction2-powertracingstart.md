---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerTracingStart
title: IWDTFSystemAction2::PowerTracingStart method
author: windows-driver-content
description: Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method is available starting with Windows 8.
old-location: dtf\iwdtfsystemaction2_powertracingstart.htm
old-project: dtf
ms.assetid: b82ebd99-289e-4761-9717-ce09cf5c40f0
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], PowerTracingStart method, IWDTFSystemAction2::PowerTracingStart, Microsoft.WDTF.IWDTFSystemAction2.PowerTracingStart, Microsoft::WDTF::IWDTFSystemAction2::PowerTracingStart, PowerTracingStart method [Windows Device Testing Framework], PowerTracingStart method [Windows Device Testing Framework], IWDTFSystemAction2 interface, PowerTracingStart,IWDTFSystemAction2.PowerTracingStart, dtf.iwdtfsystemaction2_powertracingstart, wdtfsystemaction/IWDTFSystemAction2::PowerTracingStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
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
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.PowerTracingStart
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# PowerTracingStart method
Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method
    is available starting with Windows 8.


Starts a trace for power state transitions and saves an .etl file in the current working directory

## Syntax

````
HRESULT PowerTracingStart();
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
| **Header** | wdtfsystemaction.h |

## See Also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>