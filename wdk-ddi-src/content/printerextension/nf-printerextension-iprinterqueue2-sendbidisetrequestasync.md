---
UID : NF:printerextension.IPrinterQueue2.SendBidiSetRequestAsync
title : IPrinterQueue2::SendBidiSetRequestAsync method
author : windows-driver-content
description : Uses an XML string value to send a Bidi Set request as an asynchronous operation.
old-location : print\iprinterqueue2_sendbidisetrequestasync.htm
old-project : print
ms.assetid : 05FF8A47-A586-4DA7-94AD-A7186265ADB4
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPrinterQueue2, IPrinterQueue2::SendBidiSetRequestAsync, SendBidiSetRequestAsync
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPrinterQueue2.SendBidiSetRequestAsync
req.alt-loc : Printerextension.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---


# SendBidiSetRequestAsync method
Uses an XML string value to send a Bidi Set request as an asynchronous operation.

This method allows the user to perform device maintenance tasks from within a UWP device app  for printers.

## Syntax

````
HRESULT SendBidiSetRequestAsync(
  [in]          BSTR                            bstrBidiRequest,
  [in]          IPrinterBidiSetRequestCallback  *pCallback,
  [out, retval] IPrinterExtensionAsyncOperation ** ppAsyncOperation
);
````

## Parameters

`bstrBidiRequest`

XML string that is used to transfer the data for the  Set request.

`pCallback`

Callback object for the Bidi Set request.

`ppAsyncOperation`




## Return Value

This method returns the appropriate <b>HRESULT</b> value.


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

<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterbidisetrequestcallback.md">IPrinterBidiSetRequestCallback</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterextensionasyncoperation.md">IPrinterExtensionAsyncOperation</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterqueue2.md">IPrinterQueue2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue2::SendBidiSetRequestAsync method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>