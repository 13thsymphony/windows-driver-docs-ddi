---
UID: NF:printerextension.IPrinterExtensionManager.DisableEvents
title: IPrinterExtensionManager::DisableEvents method
author: windows-driver-content
description: Disallows events to be generated.
old-location: print\iprinterextensionmanager_disableevents.htm
old-project: print
ms.assetid: 3F4C444E-8DFC-478A-B3A9-D9E7D97CF3C4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DisableEvents method [Print Devices], DisableEvents method [Print Devices], IPrinterExtensionManager interface, DisableEvents,IPrinterExtensionManager.DisableEvents, IPrinterExtensionManager, IPrinterExtensionManager interface [Print Devices], DisableEvents method, IPrinterExtensionManager::DisableEvents, print.iprinterextensionmanager_disableevents, printerextension/IPrinterExtensionManager::DisableEvents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	Printerextension.h
api_name:
-	IPrinterExtensionManager.DisableEvents
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# DisableEvents method
Disallows events to be generated.

## Syntax

````
HRESULT DisableEvents(
    Void
);
````

## Parameters

This function has no parameters.

## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8  |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterextensionmanager.md">IPrinterExtensionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406706">EnableEvents</a>