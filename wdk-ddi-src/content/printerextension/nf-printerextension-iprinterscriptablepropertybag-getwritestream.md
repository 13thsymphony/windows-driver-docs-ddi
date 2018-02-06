---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetWriteStream
title: IPrinterScriptablePropertyBag::GetWriteStream method
author: windows-driver-content
description: Gets a stream and uses it to write to a stream property.
old-location: print\iprinterscriptablepropertybag_getwritestream.htm
old-project: print
ms.assetid: EFF55B5C-55E2-4E03-9D96-FDB1BC550A53
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrinterScriptablePropertyBag, GetWriteStream method [Print Devices], IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices], GetWriteStream method, GetWriteStream, GetWriteStream method [Print Devices], printerextension/IPrinterScriptablePropertyBag::GetWriteStream, print.iprinterscriptablepropertybag_getwritestream, IPrinterScriptablePropertyBag::GetWriteStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrinterScriptablePropertyBag.GetWriteStream
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetWriteStream method
Gets a stream and uses it  to write to a stream property.

## Syntax

````
HRESULT GetWriteStream(
  [in]          BSTR                      bstrName,
  [out, retval] IPrinterScriptableStream **ppStream
);
````

## Parameters

`bstrName`

The property to write.

`ppStream`

The retrieved stream.


## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

<b>GetWriteStream</b> does not work with non-stream properties.

A call to <b>GetWriteStream</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::GetWriteStream method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>