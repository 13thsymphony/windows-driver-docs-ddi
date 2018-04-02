---
UID: NF:wudfddi.IWDFIoRequest.SetInformation
title: IWDFIoRequest::SetInformation method
author: windows-driver-content
description: The SetInformation method sets the size of information for a request.
old-location: wdf\iwdfiorequest_setinformation.htm
old-project: wdf
ms.assetid: dc2c907c-1e3b-418c-85f8-9902dc83f7ab
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest, IWDFIoRequest interface, SetInformation method, IWDFIoRequest::SetInformation, SetInformation method, SetInformation method, IWDFIoRequest interface, SetInformation,IWDFIoRequest.SetInformation, UMDFRequestObjectRef_6b29fa48-7024-44de-ab4f-68907515483a.xml, umdf.iwdfiorequest_setinformation, wdf.iwdfiorequest_setinformation, wudfddi/IWDFIoRequest::SetInformation
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
-	IWDFIoRequest.SetInformation
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequest::SetInformation method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetInformation</b> method sets the size of information for a request.

## Syntax

```
void SetInformation(
  ULONG_PTR Information
);
```

## Parameters

`Information`

A ULONG_PTR value that specifies the size of information to set for the request.


## Return Value

None


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