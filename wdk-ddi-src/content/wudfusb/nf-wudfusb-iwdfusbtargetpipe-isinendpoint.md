---
UID: NF:wudfusb.IWDFUsbTargetPipe.IsInEndPoint
title: IWDFUsbTargetPipe::IsInEndPoint method
author: windows-driver-content
description: The IsInEndPoint method determines whether a USB pipe (endpoint) is an IN pipe.
old-location: wdf\iwdfusbtargetpipe_isinendpoint.htm
old-project: wdf
ms.assetid: c1cba1fa-3952-4f2f-829f-2f5983349df8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFUsbTargetPipe, IWDFUsbTargetPipe interface, IsInEndPoint method, IWDFUsbTargetPipe::IsInEndPoint, IsInEndPoint method, IsInEndPoint method, IWDFUsbTargetPipe interface, IsInEndPoint,IWDFUsbTargetPipe.IsInEndPoint, UMDFUSBref_07580c26-1173-4624-9199-c8dc8ef59edf.xml, umdf.iwdfusbtargetpipe_isinendpoint, wdf.iwdfusbtargetpipe_isinendpoint, wudfusb/IWDFUsbTargetPipe::IsInEndPoint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetPipe.IsInEndPoint
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# IWDFUsbTargetPipe::IsInEndPoint method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsInEndPoint</b> method determines whether a USB pipe (endpoint) is an IN pipe.

## Syntax

```
BOOL IsInEndPoint(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>IsInEndPoint</b> returns a BOOL value that indicates whether the USB pipe is an IN pipe. <b>TRUE</b> indicates the pipe is an IN pipe. <b>FALSE</b> indicates the pipe is not an IN pipe.

## Remarks

If the USB pipe is an IN pipe, a UMDF driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a> method to format a read request. The framework can then send the request to the USB pipe.

<div class="alert"><b>Note</b>    The meaning of IN and OUT is opposite in WDF and USB.</div>
<div> </div>

#### Examples

For a code example of how to use the <b>IsInEndPoint</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560334">IWDFUsbInterface::GetNumEndPoints</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>