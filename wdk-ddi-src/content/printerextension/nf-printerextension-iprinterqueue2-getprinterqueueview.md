---
UID : NF:printerextension.IPrinterQueue2.GetPrinterQueueView
title : IPrinterQueue2::GetPrinterQueueView method
author : windows-driver-content
description : Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored.
old-location : print\iprinterqueue2_getprinterqueueview.htm
old-project : print
ms.assetid : C565288C-B014-4A92-9F50-1641EAA30D22
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPrinterQueue2, IPrinterQueue2::GetPrinterQueueView, GetPrinterQueueView
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
req.alt-api : IPrinterQueue2.GetPrinterQueueView
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


# GetPrinterQueueView method
Retrieves an <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

This method allows the user to perform job management tasks from within a UWP  device app for printers.

## Syntax

````
HRESULT GetPrinterQueueView(
  [in]          ULONG              ulViewOffset,
  [in]          ULONG              ulViewSize,
  [out, retval] IPrinterQueueView ** ppJobView 
);
````

## Parameters

`ulViewOffset`



`ulViewSize`



`ppJobView`




## Return Value

If the method call is successful, <b>GetPrinterQueueView</b> returns S_OK.

Otherwise, if a call to <b>GetPrinterQueueView</b> results in an error condition, then one of the following <b>HRESULT</b> values can be returned.
	  <table>
<tr>
<th>HRESULT value</th>
<th>Description</th>
</tr>
<tr>
<td>E_ILLEGAL_METHOD_CALL</td>
<td>Indicates an attempt to retrieve more than one printer queue view object.</td>
</tr>
<tr>
<td>E_INVALIDARG</td>
<td>Indicates an attempt to create a view size larger than the maximum size.</td>
</tr>
</table>

## Remarks

Only one <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object can be retrieved per <a href="..\printerextension\nn-printerextension-iprinterqueue2.md">IPrinterQueue2</a> object.
However it is possible to move around the single view that you retrieve. In other words, it is possible to  change the positions of the monitored jobs by invoking <a href="https://msdn.microsoft.com/DB3C0439-EB82-4E49-8FEA-003C1B4A9EE0">IPrinterQueueView::SetViewRange</a>.

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
<a href="..\printerextension\nn-printerextension-iprinterqueue2.md">IPrinterQueue2</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue2::GetPrinterQueueView method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>