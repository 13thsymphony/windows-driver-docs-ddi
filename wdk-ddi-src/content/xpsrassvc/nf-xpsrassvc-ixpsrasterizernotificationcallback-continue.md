---
UID: NF.xpsrassvc.IXpsRasterizerNotificationCallback.Continue
title: IXpsRasterizerNotificationCallback::Continue method
author: windows-driver-content
description: The Continue method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page.
old-location: print\ixpsrasterizernotificationcallback_continue.htm
old-project: print
ms.assetid: 8136eec2-1d4b-4233-bb93-7203d932816b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IXpsRasterizerNotificationCallback, IXpsRasterizerNotificationCallback::Continue, Continue
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
req.alt-api: IXpsRasterizerNotificationCallback.Continue
req.alt-loc: xpsrassvc.h
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
req.product: Windows 10 or later.
---

# IXpsRasterizerNotificationCallback::Continue method



## -description
The <code>Continue</code> method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page.



## -syntax

````
HRESULT Continue();
````


## -parameters


## -returns
<code>Continue</code> returns S_OK to enable rasterization to continue. Otherwise, the method returns an error code to abort rasterization. Possible error return values include:
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_PRINT_CANCELLED)</b></dt>
</dl>The current print job has been canceled.

 

<code>Continue</code> returns S_OK to enable rasterization to continue. Otherwise, the method returns an error code to abort rasterization. Possible error return values include:
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_PRINT_CANCELLED)</b></dt>
</dl>The current print job has been canceled.

 

<code>Continue</code> returns S_OK to enable rasterization to continue. Otherwise, the method returns an error code to abort rasterization. Possible error return values include:
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_PRINT_CANCELLED)</b></dt>
</dl>The current print job has been canceled.

 


## -remarks
This method is implemented by an XPSDrv filter. During a page rasterization operation, the <a href="https://msdn.microsoft.com/a6a3746a-3638-464b-bca0-60003f37af76">XPS rasterization service</a> periodically calls this method to determine whether to continue the operation.

To begin a page rasterization operation, the XPSDrv filter calls the <a href="print.ixpsrasterizer_rasterizerect">IXpsRasterizer::RasterizeRect</a> method. With this call, the filter can, as an option, supply a pointer to an <a href="print.ixpsrasterizernotificationcallback_interface">IXpsRasterizerNotificationCallback</a> interface instance. If supplied, <b>RasterizeRect</b> will periodically call the <code>Continue</code> method on this interface during the processing of the <b>RasterizeRect</b> call. If <code>Continue</code> returns a success code, <b>RasterizeRect</b> continues with the rasterization operation in progress. If <code>Continue</code> returns an error code, <b>RasterizeRect</b> aborts the rasterization operation and returns immediately.

If the user cancels a print job or if an error occurs during the processing of a print job, the pipeline manager calls the XPSDrv filter's <a href="print.iprintpipelinefilter_shutdownoperation">IPrintPipelineFilter::ShutdownOperation</a> method to shut down the filter. Typically, the filter can complete the shutdown in a more timely way if it implements the <code>Continue</code> method and supplies an <b>IXpsRasterizerNotificationCallback</b> pointer to <b>RasterizeRect</b>.

For an example implementation of the <code>Continue</code> method, see the XpsRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows 7 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Xpsrassvc.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintpipelinefilter_shutdownoperation">IPrintPipelineFilter::ShutdownOperation</a>
</dt>
<dt>
<a href="print.ixpsrasterizer_rasterizerect">IXpsRasterizer::RasterizeRect</a>
</dt>
<dt>
<a href="print.ixpsrasterizernotificationcallback_interface">IXpsRasterizerNotificationCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsRasterizerNotificationCallback::Continue method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

