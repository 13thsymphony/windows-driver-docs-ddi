---
UID: NN:printerextension.IPrinterExtensionRequest
title: IPrinterExtensionRequest
author: windows-driver-content
description: Completes the given extension event with either a cancellation or success.
old-location: print\iprinterextensionrequest_interface.htm
old-project: print
ms.assetid: 0EF8652F-34A8-4804-9D3F-8C8BEFCBCAAF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.iprinterextensionrequest_interface, IPrinterExtensionRequest interface [Print Devices], IPrinterExtensionRequest interface [Print Devices], described, IPrinterExtensionRequest, printerextension/IPrinterExtensionRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterExtensionRequest
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionRequest interface

Completes the given extension event with either a cancellation  or success.

## Methods

<p>The <b>IPrinterExtensionRequest</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [printerextension.IPrinterExtensionRequest.Cancel](nf-printerextension-iprinterextensionrequest-cancel.md) | Completes the extension event with a cancellation. |
| [printerextension.IPrinterExtensionRequest.Complete](nf-printerextension-iprinterextensionrequest-complete.md) | Completes the extension event. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/2F11C510-B649-4DC6-B0BC-89C4159E464C">IPrinterExtensionEventArgs::Request</a>

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionRequest interface%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>