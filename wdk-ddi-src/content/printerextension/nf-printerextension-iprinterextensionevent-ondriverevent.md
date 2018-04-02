---
UID: NF:printerextension.IPrinterExtensionEvent.OnDriverEvent
title: IPrinterExtensionEvent::OnDriverEvent method
author: windows-driver-content
description: Called when a driver event occurs.
old-location: print\iprinterextensionevent_ondriverevent.htm
old-project: print
ms.assetid: F00FD4FB-08D5-42D4-8CC2-85EE02D95E4B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionEvent, IPrinterExtensionEvent interface [Print Devices], OnDriverEvent method, IPrinterExtensionEvent::OnDriverEvent, OnDriverEvent method [Print Devices], OnDriverEvent method [Print Devices], IPrinterExtensionEvent interface, OnDriverEvent,IPrinterExtensionEvent.OnDriverEvent, print.iprinterextensionevent_ondriverevent, printerextension/IPrinterExtensionEvent::OnDriverEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	printerextension.h
api_name:
-	IPrinterExtensionEvent.OnDriverEvent
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterExtensionEvent::OnDriverEvent method
Called when a driver event occurs.

## Syntax

```
HRESULT OnDriverEvent(
  IPrinterExtensionEventArgs *pEventArgs
);
```

## Parameters

`pEventArgs`

The event arguments.


## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/A0F4DB51-D68E-4516-833A-7E984247796B">IPrinterExtensionEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973207">IPrinterExtensionEventArgs</a>