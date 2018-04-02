---
UID: NF:wudfusb.IWDFUsbTargetPipe.Flush
title: IWDFUsbTargetPipe::Flush method
author: windows-driver-content
description: The Flush method discards any data that WinUsb saved when the device returned more data than the client requested.
old-location: wdf\iwdfusbtargetpipe_flush.htm
old-project: wdf
ms.assetid: d8e5cbf7-62c7-458d-a527-2508a8a5d066
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Flush method, Flush method, IWDFUsbTargetPipe interface, Flush,IWDFUsbTargetPipe.Flush, IWDFUsbTargetPipe, IWDFUsbTargetPipe interface, Flush method, IWDFUsbTargetPipe::Flush, UMDFUSBref_5a569ab8-ccbd-47cc-93a6-8e61f366e6ee.xml, umdf.iwdfusbtargetpipe_flush, wdf.iwdfusbtargetpipe_flush, wudfusb/IWDFUsbTargetPipe::Flush
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
-	IWDFUsbTargetPipe.Flush
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# IWDFUsbTargetPipe::Flush method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Flush</b> method discards any data that WinUsb saved when the device returned more data than the client requested.

## Syntax

```
HRESULT Flush(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>Flush</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> successfully discarded any extra data that WinUsb saved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh463886">Flush</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the WinUsb API returned.

</td>
</tr>
</table>

## Remarks

The <b>Flush</b> method generates a UMDF request and synchronously sends the request to the I/O target.

For more information about how <b>Flush</b> works, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540227">WinUsb_FlushPipe</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560391">IWDFUsbTargetPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540227">WinUsb_FlushPipe</a>