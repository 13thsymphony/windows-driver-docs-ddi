---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetWriteParameters
title: IWDFIoRequestCompletionParams::GetWriteParameters method
author: windows-driver-content
description: The GetWriteParameters method retrieves parameters that are associated with the completion of a write request.
old-location: wdf\iwdfiorequestcompletionparams_getwriteparameters.htm
old-project: wdf
ms.assetid: 7161ba67-d94a-4f05-bb8f-a97ef418e580
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetWriteParameters method, GetWriteParameters method, IWDFIoRequestCompletionParams interface, GetWriteParameters,IWDFIoRequestCompletionParams.GetWriteParameters, IWDFIoRequestCompletionParams, IWDFIoRequestCompletionParams interface, GetWriteParameters method, IWDFIoRequestCompletionParams::GetWriteParameters, UMDFRequestObjectRef_018d6259-d6c5-4004-966a-6d18bca94057.xml, umdf.iwdfiorequestcompletionparams_getwriteparameters, wdf.iwdfiorequestcompletionparams_getwriteparameters, wudfddi/IWDFIoRequestCompletionParams::GetWriteParameters
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
-	IWDFIoRequestCompletionParams.GetWriteParameters
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequestCompletionParams::GetWriteParameters method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWriteParameters</b> method retrieves parameters that are associated with the completion of a write request.

## Syntax

```
void GetWriteParameters(
  IWDFMemory **ppWriteMemory,
  SIZE_T     *pBytesWritten,
  SIZE_T     *pWriteMemoryOffset
);
```

## Parameters

`ppWriteMemory`

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface for access to the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pBytesWritten`

A pointer to a variable that receives the size, in bytes, of the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pWriteMemoryOffset`

A pointer to a variable that receives the offset, in bytes, into the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559055">IWDFIoRequestCompletionParams</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a>