---
UID: NF:wudfddi.IWDFIoRequest2.IsFromUserModeDriver
title: IWDFIoRequest2::IsFromUserModeDriver method
author: windows-driver-content
description: The IsFromUserModeDriver method indicates whether an I/O request came from a user-mode driver or an application.
old-location: wdf\iwdfiorequest2_isfromusermodedriver.htm
old-project: wdf
ms.assetid: 17a1e4d8-5438-42b6-b4a5-335e7bd57b1b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest2, IWDFIoRequest2 interface, IsFromUserModeDriver method, IWDFIoRequest2::IsFromUserModeDriver, IsFromUserModeDriver method, IsFromUserModeDriver method, IWDFIoRequest2 interface, IsFromUserModeDriver,IWDFIoRequest2.IsFromUserModeDriver, UMDFRequestObjectRef_81f13df9-e0f7-4d16-9f85-e049a491e08d.xml, umdf.iwdfiorequest2_isfromusermodedriver, wdf.iwdfiorequest2_isfromusermodedriver, wudfddi/IWDFIoRequest2::IsFromUserModeDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFIoRequest2.IsFromUserModeDriver
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequest2::IsFromUserModeDriver method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsFromUserModeDriver</b> method indicates whether an I/O request came from a user-mode driver or an application.

## Syntax

```
BOOL IsFromUserModeDriver(

);
```

## Parameters

This function has no parameters.

## Return Value

A Boolean value that, if <b>TRUE</b>, indicates that the current I/O request is from a user-mode driver. If this value is <b>FALSE</b>, the current I/O request came from an application.

## Remarks

If your driver supports <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">kernel-mode clients</a>, it should call <b>IsFromUserModeDriver</b> only if <a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a> returns <b>WdfUserMode</b>.

The UMDF 2 equivalent of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/dn265620">WdfRequestIsFromUserModeDriver</a>.


#### Examples

For a code example that uses <b>IsFromUserModeDriver</b>, see the example at <a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265620">WdfRequestIsFromUserModeDriver</a>