---
UID: NF:wudfddi.IWDFMemory.GetSize
title: IWDFMemory::GetSize method
author: windows-driver-content
description: The GetSize method retrieves the size of the data buffer that is associated with a memory object.
old-location: wdf\iwdfmemory_getsize.htm
old-project: wdf
ms.assetid: 1ed699a3-20e5-4a1c-bce0-5a681bac9c39
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSize method, GetSize method, IWDFMemory interface, GetSize,IWDFMemory.GetSize, IWDFMemory, IWDFMemory interface, GetSize method, IWDFMemory::GetSize, UMDFMemoryObjectRef_24a9b921-5760-41fd-8b01-6a21e6be71ed.xml, umdf.iwdfmemory_getsize, wdf.iwdfmemory_getsize, wudfddi/IWDFMemory::GetSize
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
-	IWDFMemory.GetSize
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFMemory::GetSize method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetSize</b> method retrieves the size of the data buffer that is associated with a memory object.

## Syntax

```
SIZE_T GetSize(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetSize</b> returns the size, in bytes, of the data buffer for the memory object.


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