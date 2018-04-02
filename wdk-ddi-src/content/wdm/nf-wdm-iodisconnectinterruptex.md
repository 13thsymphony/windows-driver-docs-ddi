---
UID: NF:wdm.IoDisconnectInterruptEx
title: IoDisconnectInterruptEx function
author: windows-driver-content
description: For more information, see the WdmlibIoDisconnectInterruptEx function.#define IoDisconnectInterruptEx WdmlibIoDisconnectInterruptEx
old-location: kernel\iodisconnectinterruptex.htm
old-project: kernel
ms.assetid: 6c538468-2f7c-48b0-90f8-deb975c85970
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoDisconnectInterruptEx, IoDisconnectInterruptEx routine [Kernel-Mode Driver Architecture], WdmlibIoDisconnectInterruptEx, k104_3bfae096-0af6-4f61-ae4b-4c83e748b071.xml, kernel.iodisconnectinterruptex, wdm/IoDisconnectInterruptEx, wdm/WdmlibIoDisconnectInterruptEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista. Drivers that must also work Microsoft Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
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
req.lib: NtosKrnl.lib; Iointex.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoDisconnectInterruptEx
-	WdmlibIoDisconnectInterruptEx
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoDisconnectInterruptEx function
For more information, see the <a href="https://msdn.microsoft.com/B6F8663C-3A13-45DA-80FE-CC8B9194D083">WdmlibIoDisconnectInterruptEx</a> function.

<code>#define IoDisconnectInterruptEx WdmlibIoDisconnectInterruptEx</code>

## Syntax

```
NTKERNELAPI VOID IoDisconnectInterruptEx(
  PIO_DISCONNECT_INTERRUPT_PARAMETERS Parameters
);
```

## Parameters

`Parameters`

For more information, see the <a href="https://msdn.microsoft.com/B6F8663C-3A13-45DA-80FE-CC8B9194D083">WdmlibIoDisconnectInterruptEx</a> function.


## Return Value

For more information, see the <a href="https://msdn.microsoft.com/B6F8663C-3A13-45DA-80FE-CC8B9194D083">WdmlibIoDisconnectInterruptEx</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Drivers that must also work Microsoft Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib; Iointex.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/B6F8663C-3A13-45DA-80FE-CC8B9194D083">WdmlibIoDisconnectInterruptEx</a>