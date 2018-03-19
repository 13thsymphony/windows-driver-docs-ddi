---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_DetailedReasonId
title: IPrinterExtensionEventArgs::get_DetailedReasonId method
author: windows-driver-content
description: Gets a more detailed activation reason than what can be retrieved from ReasonId.
old-location: print\iprinterextensioneventargs_detailedreasonid.htm
old-project: print
ms.assetid: B39DC40A-2B7D-402F-B88C-E6684BF9AA0F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DetailedReasonId property [Print Devices], DetailedReasonId property [Print Devices], IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], DetailedReasonId property, IPrinterExtensionEventArgs.DetailedReasonId, IPrinterExtensionEventArgs::get_DetailedReasonId, get_DetailedReasonId, get_DetailedReasonId,IPrinterExtensionEventArgs.get_DetailedReasonId, print.iprinterextensioneventargs_detailedreasonid, printerextension/IPrinterExtensionEventArgs::DetailedReasonId, printerextension/IPrinterExtensionEventArgs::get_DetailedReasonId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
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
-	Printerextension.h
api_name:
-	IPrinterExtensionEventArgs.DetailedReasonId
-	IPrinterExtensionEventArgs.get_DetailedReasonId
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_DetailedReasonId method
Gets a more detailed activation reason than what can be retrieved from  <a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>.

This property is read-only.

## Syntax

````
HRESULT get_DetailedReasonId(
  [out, retval] GUID *pDetailedReasonId
);
````

## Parameters

`pDetailedReasonId`




## Return Value

None

## Remarks

The value of <b>DetailedReasonId</b> is always {5D5A1704-DFD1-4181-8EEE-815C86EDAD31}, which indicates that the printer extension was activated as  a result of a Bidi event.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>