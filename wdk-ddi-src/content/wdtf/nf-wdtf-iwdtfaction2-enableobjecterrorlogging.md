---
UID: NF:wdtf.IWDTFAction2.EnableObjectErrorLogging
title: IWDTFAction2::EnableObjectErrorLogging method
author: windows-driver-content
description: Enables object error logging for the action.
old-location: dtf\iwdtfaction2_enableobjecterrorlogging.htm
old-project: dtf
ms.assetid: 684e3c82-65f1-43fd-858a-461760dcaa8d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EnableObjectErrorLogging method [Windows Device Testing Framework], EnableObjectErrorLogging method [Windows Device Testing Framework], IWDTFAction2 interface, EnableObjectErrorLogging,IWDTFAction2.EnableObjectErrorLogging, IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], EnableObjectErrorLogging method, IWDTFAction2::EnableObjectErrorLogging, Microsoft.WDTF.IWDTFAction2.EnableObjectErrorLogging, Microsoft::WDTF::IWDTFAction2::EnableObjectErrorLogging, dtf.iwdtfaction2_enableobjecterrorlogging, wdtf/IWDTFAction2::EnableObjectErrorLogging
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
-	IWDTFAction2.EnableObjectErrorLogging
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# EnableObjectErrorLogging method
Enables object error logging for the action.

## Syntax

````
HRESULT EnableObjectErrorLogging();
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
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfaction2.md">IWDTFAction2</a>