---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.RebootRestart
title: IWDTFSystemAction2::RebootRestart method
author: windows-driver-content
description: Restart the system and the current test.
old-location: dtf\iwdtfsystemaction2_rebootrestart.htm
old-project: dtf
ms.assetid: E03A617F-BC5E-41D6-B22F-CFE9FE11D7E1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], RebootRestart method, IWDTFSystemAction2::RebootRestart, Microsoft.WDTF.IWDTFSystemAction2.RebootRestart, Microsoft::WDTF::IWDTFSystemAction2::RebootRestart, RebootRestart method [Windows Device Testing Framework], RebootRestart method [Windows Device Testing Framework], IWDTFSystemAction2 interface, RebootRestart,IWDTFSystemAction2.RebootRestart, dtf.iwdtfsystemaction2_rebootrestart, wdtfsystemaction/IWDTFSystemAction2::RebootRestart
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
-	IWDTFSystemAction2.RebootRestart
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFSystemAction2::RebootRestart method
Restart the system and the current test.

## Syntax

```
HRESULT RebootRestart(

);
```

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>