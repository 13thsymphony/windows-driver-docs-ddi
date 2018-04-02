---
UID: NF:wdtf.IWDTFCONFIG2.EnableObjectErrorLogging
title: IWDTFCONFIG2::EnableObjectErrorLogging method
author: windows-driver-content
description: Enables object error logging for all objects.
old-location: dtf\iwdtfconfig2_enableobjecterrorlogging.htm
old-project: dtf
ms.assetid: 10e7abc9-addd-4f0e-b77b-af9e8e1fa061
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EnableObjectErrorLogging method [Windows Device Testing Framework], EnableObjectErrorLogging method [Windows Device Testing Framework], IWDTFCONFIG2 interface, EnableObjectErrorLogging,IWDTFCONFIG2.EnableObjectErrorLogging, IWDTFCONFIG2, IWDTFCONFIG2 interface [Windows Device Testing Framework], EnableObjectErrorLogging method, IWDTFCONFIG2::EnableObjectErrorLogging, Microsoft.WDTF.IWDTFCONFIG2.EnableObjectErrorLogging, Microsoft::WDTF::IWDTFCONFIG2::EnableObjectErrorLogging, dtf.iwdtfconfig2_enableobjecterrorlogging, wdtf/IWDTFCONFIG2::EnableObjectErrorLogging
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFCONFIG2.EnableObjectErrorLogging
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFCONFIG2::EnableObjectErrorLogging method
Enables object error logging for all objects.

## Syntax

```
HRESULT EnableObjectErrorLogging(

);
```

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

If object logging is enabled, object error logging is enabled by default. Otherwise, error
logging defaults to disabled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406381">IWDTFCONFIG2</a>