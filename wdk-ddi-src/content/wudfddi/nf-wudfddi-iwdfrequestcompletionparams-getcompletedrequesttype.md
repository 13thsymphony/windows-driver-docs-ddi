---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetCompletedRequestType
title: IWDFRequestCompletionParams::GetCompletedRequestType method
author: windows-driver-content
description: The GetCompletedRequestType method retrieves the type of operation that the request to be completed contains.
old-location: wdf\iwdfrequestcompletionparams_getcompletedrequesttype.htm
old-project: wdf
ms.assetid: 1977828d-61bb-4649-bfa6-e5e82775258e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetCompletedRequestType method, GetCompletedRequestType method, IWDFRequestCompletionParams interface, GetCompletedRequestType,IWDFRequestCompletionParams.GetCompletedRequestType, IWDFRequestCompletionParams, IWDFRequestCompletionParams interface, GetCompletedRequestType method, IWDFRequestCompletionParams::GetCompletedRequestType, UMDFRequestObjectRef_97c61d1b-059f-44d7-9d3a-7c031099d669.xml, umdf.iwdfrequestcompletionparams_getcompletedrequesttype, wdf.iwdfrequestcompletionparams_getcompletedrequesttype, wudfddi/IWDFRequestCompletionParams::GetCompletedRequestType
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
-	IWDFRequestCompletionParams.GetCompletedRequestType
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFRequestCompletionParams::GetCompletedRequestType method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCompletedRequestType</b> method retrieves the type of operation that the request to be completed contains.

## Syntax

```
WDF_REQUEST_TYPE GetCompletedRequestType(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetCompletedRequestType</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>-typed value that identifies the request type and why the request was sent to the driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552503">WDF_REQUEST_TYPE</a>