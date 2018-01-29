---
UID : NF:printerextension.IPrintJob.RequestCancel
title : IPrintJob::RequestCancel method
author : windows-driver-content
description : Requests the cancellation of a print job.
old-location : print\iprintjob_requestcancel.htm
old-project : print
ms.assetid : 13F8A151-F28A-4A0F-B143-F3DB2197A36B
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : printerextension/IPrintJob::RequestCancel, print.iprintjob_requestcancel, RequestCancel, IPrintJob interface [Print Devices], RequestCancel method, RequestCancel method [Print Devices], IPrintJob interface, RequestCancel method [Print Devices], IPrintJob::RequestCancel, IPrintJob
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


# RequestCancel method
Requests the cancellation of a print job.

## Syntax

````
HRESULT RequestCancel(
    void
);
````

## Parameters

This function has no parameters.

## Return Value

Returns an <b>HRESULT</b> value. If the method call was not successful, it returns the appropriate <b>HRESULT</b> error code.

## Remarks

The <b>RequestCancel</b> method does not wait for the cancellation of a print job to be processed to completion before it returns.

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

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob::RequestCancel method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>