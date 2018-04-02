---
UID: NF:printerextension.IPrintJob.RequestCancel
title: IPrintJob::RequestCancel method
author: windows-driver-content
description: Requests the cancellation of a print job.
old-location: print\iprintjob_requestcancel.htm
old-project: print
ms.assetid: 13F8A151-F28A-4A0F-B143-F3DB2197A36B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], RequestCancel method, IPrintJob::RequestCancel, RequestCancel method [Print Devices], RequestCancel method [Print Devices], IPrintJob interface, RequestCancel,IPrintJob.RequestCancel, print.iprintjob_requestcancel, printerextension/IPrintJob::RequestCancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrintJob.RequestCancel
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintJob::RequestCancel method
Requests the cancellation of a print job.

## Syntax

```
HRESULT RequestCancel(

);
```

## Parameters

This function has no parameters.

## Return Value

Returns an <b>HRESULT</b> value. If the method call was not successful, it returns the appropriate <b>HRESULT</b> error code.

## Remarks

The <b>RequestCancel</b> method does not wait for the cancellation of a print job to be processed to completion before it returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265396">IPrintJob</a>