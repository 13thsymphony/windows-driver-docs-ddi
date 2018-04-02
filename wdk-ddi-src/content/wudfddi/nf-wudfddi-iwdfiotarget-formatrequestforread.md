---
UID: NF:wudfddi.IWDFIoTarget.FormatRequestForRead
title: IWDFIoTarget::FormatRequestForRead method
author: windows-driver-content
description: The FormatRequestForRead method formats an I/O request object for a read operation.
old-location: wdf\iwdfiotarget_formatrequestforread.htm
old-project: wdf
ms.assetid: 8a1b61c8-8b85-4224-ae20-3788eb0babe4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FormatRequestForRead method, FormatRequestForRead method, IWDFIoTarget interface, FormatRequestForRead,IWDFIoTarget.FormatRequestForRead, IWDFIoTarget, IWDFIoTarget interface, FormatRequestForRead method, IWDFIoTarget::FormatRequestForRead, UMDFIoTargetObjectRef_49d4b6d7-0cd7-4d8a-9b16-7ecc89f82f1e.xml, umdf.iwdfiotarget_formatrequestforread, wdf.iwdfiotarget_formatrequestforread, wudfddi/IWDFIoTarget::FormatRequestForRead
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
-	IWDFIoTarget.FormatRequestForRead
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoTarget::FormatRequestForRead method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForRead</b> method formats an I/O request object for a read operation.

## Syntax

```
HRESULT FormatRequestForRead(
  IWDFIoRequest     *pRequest,
  IWDFFile          *pFile,
  IWDFMemory        *pOutputMemory,
  PWDFMEMORY_OFFSET pOutputMemoryOffset,
  PLONGLONG         DeviceOffset
);
```

## Parameters

`pRequest`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface for the request object to format.

`pFile`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the file object that is associated with the read request. For the default I/O target, this parameter must be non-NULL.

`pOutputMemory`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface that is used to access the buffer that is used for the read request. This parameter is optional.

`pOutputMemoryOffset`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure that describes the output memory offset that is used for the read. This parameter is optional.

`DeviceOffset`

A pointer to the device offset that is used for the read. This parameter is optional.


## Return Value

<b>FormatRequestForRead</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a>