---
UID: NF:wdtf.IWDTFCONFIG2.EnableObjectLogging
title: IWDTFCONFIG2::EnableObjectLogging method
author: windows-driver-content
description: Enables object logging for all objects.
old-location: dtf\iwdtfconfig2_enableobjectlogging.htm
old-project: dtf
ms.assetid: 7518aab0-8de5-4f45-b7d9-3cffdc07ea90
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EnableObjectLogging method [Windows Device Testing Framework], EnableObjectLogging method [Windows Device Testing Framework], IWDTFCONFIG2 interface, EnableObjectLogging,IWDTFCONFIG2.EnableObjectLogging, IWDTFCONFIG2, IWDTFCONFIG2 interface [Windows Device Testing Framework], EnableObjectLogging method, IWDTFCONFIG2::EnableObjectLogging, Microsoft.WDTF.IWDTFCONFIG2.EnableObjectLogging, Microsoft::WDTF::IWDTFCONFIG2::EnableObjectLogging, dtf.iwdtfconfig2_enableobjectlogging, wdtf/IWDTFCONFIG2::EnableObjectLogging
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
req.lib: wdtf.h
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
-	IWDTFCONFIG2.EnableObjectLogging
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# EnableObjectLogging method
Enables object logging for all objects.

## Syntax

````
HRESULT EnableObjectLogging();
````

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

<b>WDTF</b> object logging defaults to disabled. If object logging is enabled, 
each <b>WDTF</b> object writes to the 
test scripts log.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |
| **Library** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfconfig2.md">IWDTFCONFIG2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFCONFIG2::EnableObjectLogging method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>