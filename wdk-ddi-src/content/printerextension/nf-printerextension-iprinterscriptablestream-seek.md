---
UID: NF:printerextension.IPrinterScriptableStream.Seek
title: IPrinterScriptableStream::Seek method
author: windows-driver-content
description: Sets the seek pointer.
old-location: print\iprinterscriptablestream__seek.htm
old-project: print
ms.assetid: 82080353-2252-4BF2-B7F4-F297DCA99FA0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterScriptableStream, IPrinterScriptableStream interface [Print Devices], Seek method, IPrinterScriptableStream::Seek, Seek method [Print Devices], Seek method [Print Devices], IPrinterScriptableStream interface, Seek,IPrinterScriptableStream.Seek, print.iprinterscriptablestream__seek, printerextension/IPrinterScriptableStream::Seek
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
-	IPrinterScriptableStream.Seek
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterScriptableStream::Seek method
Sets the seek pointer.

## Syntax

```
HRESULT Seek(
  LONG        lOffset,
  STREAM_SEEK streamSeek,
  LONG        *plPosition
);
```

## Parameters

`lOffset`

The displacement to be added to the location indicated by the <i>streamSeek</i> parameter.

`streamSeek`

The origin for the displacement specified <i>lOffset</i>.

`plPosition`

The new pointer position.


## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh973218">IPrinterScriptableStream</a>