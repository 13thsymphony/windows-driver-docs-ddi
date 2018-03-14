---
UID: NF:printerextension.IPrintJob.get_Name
title: IPrintJob::get_Name method
author: windows-driver-content
description: Gets the name of the printer for this print queue.
old-location: print\iprinterqueue_name.htm
old-project: print
ms.assetid: BB8CAEFC-3CD5-46EA-89A8-FAF38063A185
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob::get_Name, IPrinterQueue interface [Print Devices], Name property, IPrinterQueue.Name, IPrinterQueue::get_Name, Name property [Print Devices], Name property [Print Devices], IPrinterQueue interface, get_Name, get_Name,IPrintJob.get_Name, print.iprinterqueue_name, printerextension/IPrinterQueue::Name, printerextension/IPrinterQueue::get_Name
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	IPrinterQueue.Name
-	IPrinterQueue.get_Name
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_Name method
Gets the name of the printer for this print queue.

This property is read-only.

## Syntax

````
HRESULT get_Name(
  [out, retval] BSTR *pbstrName
);
````

## Parameters

`pbstrName`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue::Name property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>