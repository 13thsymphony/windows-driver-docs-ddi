---
UID: NF:wudfddi.IWDFMemory.GetDataBuffer
title: IWDFMemory::GetDataBuffer method
author: windows-driver-content
description: The GetDataBuffer method retrieves the data buffer that is associated with a memory object.
old-location: wdf\iwdfmemory_getdatabuffer.htm
old-project: wdf
ms.assetid: 136aa2af-e3bf-48b6-9511-348510eedfb5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetDataBuffer method, GetDataBuffer method, IWDFMemory interface, GetDataBuffer,IWDFMemory.GetDataBuffer, IWDFMemory, IWDFMemory interface, GetDataBuffer method, IWDFMemory::GetDataBuffer, UMDFMemoryObjectRef_910791a8-4fd9-47ff-93f9-f8f496e95272.xml, umdf.iwdfmemory_getdatabuffer, wdf.iwdfmemory_getdatabuffer, wudfddi/IWDFMemory::GetDataBuffer
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
-	IWDFMemory.GetDataBuffer
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFMemory::GetDataBuffer method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDataBuffer</b> method retrieves the data buffer that is associated with a memory object.

## Syntax

```
void * GetDataBuffer(
  SIZE_T *BufferSize
);
```

## Parameters

`BufferSize`




## Return Value

<b>GetDataBuffer</b> returns a pointer to the data buffer.

## Remarks

For a code example of how to use the <b>GetDataBuffer</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a>