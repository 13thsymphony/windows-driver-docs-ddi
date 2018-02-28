---
UID: NF:wdtf.IWDTFLOG2.OutputInfo
title: IWDTFLOG2::OutputInfo method
author: windows-driver-content
description: Writes an informational entry to the test case log.
old-location: dtf\iwdtflog2_outputinfo.htm
old-project: dtf
ms.assetid: bd98186f-5681-4611-9c27-eabfe4412df7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFLOG2, IWDTFLOG2 interface [Windows Device Testing Framework], OutputInfo method, IWDTFLOG2::OutputInfo, Microsoft.WDTF.IWDTFLOG2.OutputInfo, Microsoft::WDTF::IWDTFLOG2::OutputInfo, OutputInfo method [Windows Device Testing Framework], OutputInfo method [Windows Device Testing Framework], IWDTFLOG2 interface, OutputInfo,IWDTFLOG2.OutputInfo, dtf.iwdtflog2_outputinfo, wdtf/IWDTFLOG2::OutputInfo
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
-	IWDTFLOG2.OutputInfo
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# OutputInfo method
Writes an informational entry to the test case log.

## Syntax

````
HRESULT OutputInfo(
  [in] BSTR sInfoString
);
````

## Parameters

`sInfoString`

The information string.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |
| **Library** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtflog2.md">IWDTFLOG2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFLOG2::OutputInfo method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>