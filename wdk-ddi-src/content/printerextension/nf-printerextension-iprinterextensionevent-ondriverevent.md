---
UID: NF:printerextension.IPrinterExtensionEvent.OnDriverEvent
title: IPrinterExtensionEvent::OnDriverEvent method
author: windows-driver-content
description: Called when a driver event occurs.
old-location: print\iprinterextensionevent_ondriverevent.htm
old-project: print
ms.assetid: F00FD4FB-08D5-42D4-8CC2-85EE02D95E4B
ms.author: windowsdriverdev
ms.date: 2/23/2018
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
req.lib: printerextension.h
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
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# OnDriverEvent method
Called when a driver event occurs.

## Syntax

````
HRESULT OnDriverEvent(
  [in] IPrinterExtensionEventArgs *pEventArgs
);
````

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
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterextensionevent.md">IPrinterExtensionEvent</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEvent::OnDriverEvent method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>