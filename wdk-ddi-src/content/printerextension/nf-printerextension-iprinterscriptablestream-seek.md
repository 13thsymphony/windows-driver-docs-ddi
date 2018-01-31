---
UID : NF:printerextension.IPrinterScriptableStream.Seek
title : IPrinterScriptableStream::Seek method
author : windows-driver-content
description : Sets the seek pointer.
old-location : print\iprinterscriptablestream__seek.htm
old-project : print
ms.assetid : 82080353-2252-4BF2-B7F4-F297DCA99FA0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : Seek method [Print Devices], IPrinterScriptableStream interface [Print Devices], Seek method, IPrinterScriptableStream, print.iprinterscriptablestream__seek, Seek method [Print Devices], IPrinterScriptableStream interface, IPrinterScriptableStream::Seek, printerextension/IPrinterScriptableStream::Seek, Seek
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : printerextension.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---


# Seek method
Sets the seek pointer.

## Syntax

````
HRESULT Seek(
  [in]          LONG        lOffset,
  [in]          STREAM_SEEK streamSeek,
  [out, retval] LONG        *plPosition
);
````

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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printerextension.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablestream.md">IPrinterScriptableStream</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptableStream::Seek method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>