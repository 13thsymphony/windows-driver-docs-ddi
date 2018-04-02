---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetIoctlParameters
title: IWDFIoRequestCompletionParams::GetIoctlParameters method
author: windows-driver-content
description: The GetIoctlParameters method retrieves parameters that are associated with the completion of a device I/O control request.
old-location: wdf\iwdfiorequestcompletionparams_getioctlparameters.htm
old-project: wdf
ms.assetid: 59e2cd27-ec10-46e9-aa0d-4a00e2684e76
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetIoctlParameters method, GetIoctlParameters method, IWDFIoRequestCompletionParams interface, GetIoctlParameters,IWDFIoRequestCompletionParams.GetIoctlParameters, IWDFIoRequestCompletionParams, IWDFIoRequestCompletionParams interface, GetIoctlParameters method, IWDFIoRequestCompletionParams::GetIoctlParameters, UMDFRequestObjectRef_7d375866-617c-418f-b449-7931a88e7ae4.xml, umdf.iwdfiorequestcompletionparams_getioctlparameters, wdf.iwdfiorequestcompletionparams_getioctlparameters, wudfddi/IWDFIoRequestCompletionParams::GetIoctlParameters
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
-	IWDFIoRequestCompletionParams.GetIoctlParameters
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequestCompletionParams::GetIoctlParameters method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetIoctlParameters</b> method retrieves parameters that are associated with the completion of a device I/O control request.

## Syntax

```
void GetIoctlParameters(
  ULONG      *pIoControlCode,
  IWDFMemory **ppInputMemory,
  SIZE_T     *pInputMemoryOffset,
  IWDFMemory **ppOutputMemory,
  SIZE_T     *pOutputMemoryOffset,
  SIZE_T     *pOutBytes
);
```

## Parameters

`pIoControlCode`

A pointer to a variable that receives the control code that identifies the specific operation to be performed. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`ppInputMemory`

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface for access to the input buffer for the completion of the device I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pInputMemoryOffset`

A pointer to a variable that receives the offset, in bytes, into the input buffer for the completion of the I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`ppOutputMemory`

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface for access to the output buffer for the completion of the device I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pOutputMemoryOffset`

A pointer to a variable that receives the offset, in bytes, into the output buffer for the completion of the I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information.

`pOutBytes`

A pointer to a variable that receives the number of bytes that are output for the completion of the device I/O control request.

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