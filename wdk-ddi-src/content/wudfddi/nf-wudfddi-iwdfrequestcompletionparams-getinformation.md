---
UID: NF:wudfddi.IWDFRequestCompletionParams.GetInformation
title: IWDFRequestCompletionParams::GetInformation method
author: windows-driver-content
description: The GetInformation method retrieves information that is associated with the completion of an I/O request.
old-location: wdf\iwdfrequestcompletionparams_getinformation.htm
old-project: wdf
ms.assetid: 6dd47575-0da3-4038-81aa-ac955c00f08d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetInformation method, GetInformation method, IWDFRequestCompletionParams interface, GetInformation,IWDFRequestCompletionParams.GetInformation, IWDFRequestCompletionParams, IWDFRequestCompletionParams interface, GetInformation method, IWDFRequestCompletionParams::GetInformation, UMDFRequestObjectRef_f014a31c-ac37-419d-a318-31d910c646b1.xml, umdf.iwdfrequestcompletionparams_getinformation, wdf.iwdfrequestcompletionparams_getinformation, wudfddi/IWDFRequestCompletionParams::GetInformation
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
-	IWDFRequestCompletionParams.GetInformation
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFRequestCompletionParams::GetInformation method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetInformation</b> method retrieves information that is associated with the completion of an I/O request.

## Syntax

```
ULONG_PTR GetInformation(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetInformation</b> returns information (for example, the number of bytes transferred) that is associated with the completion of the I/O request.


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