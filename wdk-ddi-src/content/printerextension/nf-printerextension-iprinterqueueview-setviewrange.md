---
UID: NF:printerextension.IPrinterQueueView.SetViewRange
title: IPrinterQueueView::SetViewRange method
author: windows-driver-content
description: Sets the range of print jobs being monitored.
old-location: print\iprinterqueueview_setviewrange.htm
old-project: print
ms.assetid: DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterQueueView, IPrinterQueueView interface [Print Devices], SetViewRange method, IPrinterQueueView::SetViewRange, SetViewRange method [Print Devices], SetViewRange method [Print Devices], IPrinterQueueView interface, SetViewRange,IPrinterQueueView.SetViewRange, print.iprinterqueueview_setviewrange, printerextension/IPrinterQueueView::SetViewRange
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
-	IPrinterQueueView.SetViewRange
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# SetViewRange method
Sets the range of print jobs being monitored.

## Syntax

````
HRESULT SetViewRange(
  [in] ULONG ulViewOffset,
  [in] ULONG ulViewSize
);
````

## Parameters

`ulViewOffset`

The start of the range of jobs being monitored. Note that the offset value uses a zero-based index.

`ulViewSize`

The  size of the range of jobs being monitored.


## Return Value

This method returns the appropriate <b>HRESULT</b> value.

## Remarks

Invoking this method causes the events for status change to the jobs to be fired. The <a href="https://msdn.microsoft.com/D964A0C4-041A-47BD-87AB-4AF523939DF0">IPrinterQueueViewEvent::OnChanged</a> event method returns the live queue in response, using the specified maximum range size.

<div class="alert"><b>Note</b>  <i>ulViewSize</i> must be specified as a value less than or equal to 25. If the caller specifies a size which exceeds 25,  this method will return E_INVALIDARG.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/D964A0C4-041A-47BD-87AB-4AF523939DF0">IPrinterQueueViewEvent::OnChanged</a>



<a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a>



<a href="https://msdn.microsoft.com/C565288C-B014-4A92-9F50-1641EAA30D22">IPrinterQueue2::GetPrinterQueueView</a>