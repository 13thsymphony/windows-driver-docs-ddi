---
UID: NF:wudfddi.IWDFMemory.SetBuffer
title: IWDFMemory::SetBuffer method
author: windows-driver-content
description: The SetBuffer method assigns a specified buffer to a memory object that a driver created by calling IWDFDriver::CreatePreallocatedWdfMemory.
old-location: wdf\iwdfmemory_setbuffer.htm
old-project: wdf
ms.assetid: 1399922d-684c-44a4-8bc7-b9e45ba05086
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFMemory, IWDFMemory interface, SetBuffer method, IWDFMemory::SetBuffer, SetBuffer method, SetBuffer method, IWDFMemory interface, SetBuffer,IWDFMemory.SetBuffer, UMDFMemoryObjectRef_34339a6a-7426-46fc-8df9-7f5281b03308.xml, umdf.iwdfmemory_setbuffer, wdf.iwdfmemory_setbuffer, wudfddi/IWDFMemory::SetBuffer
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
-	IWDFMemory.SetBuffer
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# SetBuffer method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetBuffer</b> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>.

## Syntax

````
void SetBuffer(
  [in] void   *Buffer,
  [in] SIZE_T BufferSize
);
````

## Parameters

`Buffer`

A pointer to a driver-supplied buffer.

`BufferSize`

The nonzero size, in bytes, of the buffer that <i>Buffer</i> points to.


## Return Value

None

## Remarks

The <b>SetBuffer</b> method can assign a buffer to a memory object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a> created, but not to a memory object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a> created.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>