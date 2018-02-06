---
UID: NF:wdm.MmSizeOfMdl
title: MmSizeOfMdl function
author: windows-driver-content
description: The MmSizeOfMdl routine returns the number of bytes to allocate for an MDL describing a given address range.
old-location: kernel\mmsizeofmdl.htm
old-project: kernel
ms.assetid: 83e7d4be-df76-4dc8-a8e2-91d279127ef1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/MmSizeOfMdl, MmSizeOfMdl, MmSizeOfMdl routine [Kernel-Mode Driver Architecture], kernel.mmsizeofmdl, k106_7cddc848-8b01-4a6a-b5b1-977f2386fc21.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmSizeOfMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmSizeOfMdl function
The <b>MmSizeOfMdl</b> routine returns the number of bytes to allocate for an MDL describing a given address range.

## Syntax

````
SIZE_T MmSizeOfMdl(
  _In_ PVOID  Base,
  _In_ SIZE_T Length
);
````

## Parameters

`Base`

Pointer to the base virtual address for the range.

`Length`

Supplies the size, in bytes, of the range.


## Return Value

<b>MmSizeOfMdl</b> returns the number of bytes required to contain the MDL.

## Remarks

Memory for the MDL itself must be allocated from nonpaged pool.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554500">MmCreateMdl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554568">MmInitializeMdl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmSizeOfMdl routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>