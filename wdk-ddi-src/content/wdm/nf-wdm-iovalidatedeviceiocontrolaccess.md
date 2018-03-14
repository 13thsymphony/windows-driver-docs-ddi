---
UID: NF:wdm.IoValidateDeviceIoControlAccess
title: IoValidateDeviceIoControlAccess function
author: windows-driver-content
description: For more information, see the WdmlibIoValidateDeviceIoControlAccess function.
old-location: kernel\iovalidatedeviceiocontrolaccess.htm
old-project: kernel
ms.assetid: 45e8279f-b7a5-4b45-92b7-5f740f6c1117
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoValidateDeviceIoControlAccess, IoValidateDeviceIoControlAccess routine [Kernel-Mode Driver Architecture], k104_724cb845-fabf-4b5a-8712-901829f1f79d.xml, kernel.iovalidatedeviceiocontrolaccess, wdm/IoValidateDeviceIoControlAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows. Drivers that must also work for Windows 2000 and Windows XP can instead link to Wdmsec.lib to use this routine. (The Wdmsec.lib library first shipped with the Windows XP Service Pack 1 [SP1] and Windows Server 2003 editions of the Driver Development Kit [DDK] and now ships with the Windows Driver Kit [WDK].)
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoValidateDeviceIoControlAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoValidateDeviceIoControlAccess function
For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibiovalidatedeviceiocontrolaccess.md">WdmlibIoValidateDeviceIoControlAccess</a> function.

## Syntax

````
NTSTATUS IoValidateDeviceIoControlAccess(
  _In_ PIRP  Irp,
  _In_ ULONG RequiredAccess
);
````

## Parameters

`Irp`

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibiovalidatedeviceiocontrolaccess.md">WdmlibIoValidateDeviceIoControlAccess</a> function.

`RequiredAccess`

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibiovalidatedeviceiocontrolaccess.md">WdmlibIoValidateDeviceIoControlAccess</a> function.


## Return Value

For more information, see  the <a href="..\wdmsec\nf-wdmsec-wdmlibiovalidatedeviceiocontrolaccess.md">WdmlibIoValidateDeviceIoControlAccess</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows. Drivers that must also work for Windows 2000 and Windows XP can instead link to Wdmsec.lib to use this routine. (The Wdmsec.lib library first shipped with the Windows XP Service Pack 1 [SP1] and Windows Server 2003 editions of the Driver Development Kit [DDK] and now ships with the Windows Driver Kit [WDK].)  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoValidateDeviceIoControlAccess routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>