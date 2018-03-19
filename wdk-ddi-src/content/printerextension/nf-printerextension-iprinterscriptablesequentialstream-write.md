---
UID: NF:printerextension.IPrinterScriptableSequentialStream.Write
title: IPrinterScriptableSequentialStream::Write method
author: windows-driver-content
description: The Write method writes the provided JavaScript array to the stream and returns the number of bytes written.
old-location: print\iprinterscriptablesequentialstream_write.htm
old-project: print
ms.assetid: 1140F881-A6E1-4342-A069-BE9EB3BD4BF8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterScriptableSequentialStream, IPrinterScriptableSequentialStream interface [Print Devices], Write method, IPrinterScriptableSequentialStream::Write, Write method [Print Devices], Write method [Print Devices], IPrinterScriptableSequentialStream interface, Write,IPrinterScriptableSequentialStream.Write, print.iprinterscriptablesequentialstream_write, printerextension/IPrinterScriptableSequentialStream::Write
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
-	printerextension.h
api_name:
-	IPrinterScriptableSequentialStream.Write
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# Write method
The Write method writes the provided JavaScript array to the stream and returns the number of bytes written.

## Syntax

````
HRESULT Write(
  [in]          IDispatch *pdispArray,
  [out, retval] LONG      *pcbWritten
);
````

## Parameters

`pArray`



`pcbWritten`

The number of bytes written.


## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8  |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablesequentialstream.md">IPrinterScriptableSequentialStream</a>