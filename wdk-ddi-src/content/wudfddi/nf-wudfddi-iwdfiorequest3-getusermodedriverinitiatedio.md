---
UID: NF:wudfddi.IWDFIoRequest3.GetUserModeDriverInitiatedIo
title: IWDFIoRequest3::GetUserModeDriverInitiatedIo method
author: windows-driver-content
description: The GetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver.
old-location: wdf\iwdfiorequest3_getusermodedriverinitiatedio.htm
old-project: wdf
ms.assetid: 41C4E9D2-DC1B-4DFC-8C15-E9C21515B5F0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetUserModeDriverInitiatedIo method, GetUserModeDriverInitiatedIo method, IWDFIoRequest3 interface, GetUserModeDriverInitiatedIo,IWDFIoRequest3.GetUserModeDriverInitiatedIo, IWDFIoRequest3, IWDFIoRequest3 interface, GetUserModeDriverInitiatedIo method, IWDFIoRequest3::GetUserModeDriverInitiatedIo, umdf.iwdfiorequest3_getusermodedriverinitiatedio, wdf.iwdfiorequest3_getusermodedriverinitiatedio, wudfddi/IWDFIoRequest3::GetUserModeDriverInitiatedIo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFIoRequest3.GetUserModeDriverInitiatedIo
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequest3::GetUserModeDriverInitiatedIo method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>GetUserModeDriverInitiatedIo</b> method determines whether an I/O request is marked as initiated by a UMDF driver.

## Syntax

```
BOOL GetUserModeDriverInitiatedIo(

);
```

## Parameters

This function has no parameters.

## Return Value

The method returns <b>TRUE</b> if the request is marked as UMDF driver-initiated and <b>FALSE</b> if the request is not marked as UMDF driver-initiated.

## Remarks

For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>.

The UMDF 2 equivalent of this method is <a href="https://msdn.microsoft.com/library/windows/hardware/dn265618">WdfRequestGetUserModeInitiatedIo</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451337">IWDFIoRequest3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>