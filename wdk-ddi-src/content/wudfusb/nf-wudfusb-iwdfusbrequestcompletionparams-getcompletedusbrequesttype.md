---
UID: NF:wudfusb.IWDFUsbRequestCompletionParams.GetCompletedUsbRequestType
title: IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType method
author: windows-driver-content
description: The GetCompletedUsbRequestType method retrieves the type of operation that the request to be completed contains.
old-location: wdf\iwdfusbrequestcompletionparams_getcompletedusbrequesttype.htm
old-project: wdf
ms.assetid: ce20ed09-2f4d-4cc0-9185-a3a72dd73165
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetCompletedUsbRequestType method, GetCompletedUsbRequestType method, IWDFUsbRequestCompletionParams interface, GetCompletedUsbRequestType,IWDFUsbRequestCompletionParams.GetCompletedUsbRequestType, IWDFUsbRequestCompletionParams, IWDFUsbRequestCompletionParams interface, GetCompletedUsbRequestType method, IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType, UMDFRequestObjectRef_9b863f1d-1684-4d87-a7a0-41747dba6aff.xml, umdf.iwdfusbrequestcompletionparams_getcompletedusbrequesttype, wdf.iwdfusbrequestcompletionparams_getcompletedusbrequesttype, wudfusb/IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType
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
-	IWDFUsbRequestCompletionParams.GetCompletedUsbRequestType
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---


# IWDFUsbRequestCompletionParams::GetCompletedUsbRequestType method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletedUsbRequestType</b> method retrieves the type of operation that the request to be completed contains.

## Syntax

```
WDF_USB_REQUEST_TYPE GetCompletedUsbRequestType(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetCompletedUsbRequestType</b> returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553055">WDF_USB_REQUEST_TYPE</a> that identifies the USB request type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfusb.h (include Wudfusb.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560346">IWDFUsbRequestCompletionParams</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553055">WDF_USB_REQUEST_TYPE</a>