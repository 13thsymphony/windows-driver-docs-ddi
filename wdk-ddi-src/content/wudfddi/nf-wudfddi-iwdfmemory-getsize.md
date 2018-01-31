---
UID : NF:wudfddi.IWDFMemory.GetSize
title : IWDFMemory::GetSize method
author : windows-driver-content
description : The GetSize method retrieves the size of the data buffer that is associated with a memory object.
old-location : wdf\iwdfmemory_getsize.htm
old-project : wdf
ms.assetid : 1ed699a3-20e5-4a1c-bce0-5a681bac9c39
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFMemory, umdf.iwdfmemory_getsize, GetSize method, wdf.iwdfmemory_getsize, IWDFMemory interface, GetSize method, GetSize, wudfddi/IWDFMemory::GetSize, GetSize method, IWDFMemory interface, IWDFMemory::GetSize, UMDFMemoryObjectRef_24a9b921-5760-41fd-8b01-6a21e6be71ed.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# GetSize method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetSize</b> method retrieves the size of the data buffer that is associated with a memory object.

## Syntax

````
SIZE_T  GetSize();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetSize</b> returns the size, in bytes, of the data buffer for the memory object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFMemory::GetSize method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>