---
UID: NF:wudfddi.IWDFIoRequest.GetType
title: IWDFIoRequest::GetType method
author: windows-driver-content
description: The GetType method retrieves the type of operation that a request contains.
old-location: wdf\iwdfiorequest_gettype.htm
old-project: wdf
ms.assetid: 3be2ef6c-391e-4d1c-a1a6-e3228f5cc67d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetType method, GetType method, IWDFIoRequest interface, GetType,IWDFIoRequest.GetType, IWDFIoRequest, IWDFIoRequest interface, GetType method, IWDFIoRequest::GetType, UMDFRequestObjectRef_8f8bc7b0-b527-4325-a2dc-a9ef5e73cc28.xml, umdf.iwdfiorequest_gettype, wdf.iwdfiorequest_gettype, wudfddi/IWDFIoRequest::GetType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
-	IWDFIoRequest.GetType
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequest::GetType method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetType</b> method retrieves the type of operation that a request contains.

## Syntax

```
WDF_REQUEST_TYPE GetType(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetType</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>-typed value that identifies the request type and why the request is sent to the driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>