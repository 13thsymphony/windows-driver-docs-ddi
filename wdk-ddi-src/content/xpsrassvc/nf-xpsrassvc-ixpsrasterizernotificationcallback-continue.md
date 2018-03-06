---
UID: NF:xpsrassvc.IXpsRasterizerNotificationCallback.Continue
title: IXpsRasterizerNotificationCallback::Continue method
author: windows-driver-content
description: The Continue method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page.
old-location: print\ixpsrasterizernotificationcallback_continue.htm
old-project: print
ms.assetid: 8136eec2-1d4b-4233-bb93-7203d932816b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Continue method [Print Devices], Continue method [Print Devices], IXpsRasterizerNotificationCallback interface, Continue,IXpsRasterizerNotificationCallback.Continue, IXpsRasterizerNotificationCallback, IXpsRasterizerNotificationCallback interface [Print Devices], Continue method, IXpsRasterizerNotificationCallback::Continue, print.ixpsrasterizernotificationcallback_continue, print_xpsrast_f107f6a3-c35f-4ec1-b50f-062852852af6.xml, xpsrassvc/IXpsRasterizerNotificationCallback::Continue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: xpsrassvc.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
req.lib: xpsrassvc.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	xpsrassvc.h
api_name:
-	IXpsRasterizerNotificationCallback.Continue
product: Windows
targetos: Windows
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---


# Continue method
The <code>Continue</code> method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page.

## Syntax

````
HRESULT Continue();
````

## Parameters

This function has no parameters.

## Return Value

<code>Continue</code> returns S_OK to enable rasterization to continue. Otherwise, the method returns an error code to abort rasterization. Possible error return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_PRINT_CANCELLED)</b></dt>
</dl>
</td>
<td width="60%">
The current print job has been canceled.

</td>
</tr>
</table>

## Remarks

This method is implemented by an XPSDrv filter. During a page rasterization operation, the <a href="https://msdn.microsoft.com/a6a3746a-3638-464b-bca0-60003f37af76">XPS rasterization service</a> periodically calls this method to determine whether to continue the operation.

To begin a page rasterization operation, the XPSDrv filter calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a> method. With this call, the filter can, as an option, supply a pointer to an <a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizernotificationcallback.md">IXpsRasterizerNotificationCallback</a> interface instance. If supplied, <b>RasterizeRect</b> will periodically call the <code>Continue</code> method on this interface during the processing of the <b>RasterizeRect</b> call. If <code>Continue</code> returns a success code, <b>RasterizeRect</b> continues with the rasterization operation in progress. If <code>Continue</code> returns an error code, <b>RasterizeRect</b> aborts the rasterization operation and returns immediately.

If the user cancels a print job or if an error occurs during the processing of a print job, the pipeline manager calls the XPSDrv filter's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554295">IPrintPipelineFilter::ShutdownOperation</a> method to shut down the filter. Typically, the filter can complete the shutdown in a more timely way if it implements the <code>Continue</code> method and supplies an <b>IXpsRasterizerNotificationCallback</b> pointer to <b>RasterizeRect</b>.

For an example implementation of the <code>Continue</code> method, see the XpsRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows 7 and later versions of the Windows operating system.  |
| **Target Platform** | Desktop |
| **Header** | xpsrassvc.h |
| **Library** | xpsrassvc.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554295">IPrintPipelineFilter::ShutdownOperation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>



<a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizernotificationcallback.md">IXpsRasterizerNotificationCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsRasterizerNotificationCallback::Continue method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>