---
UID: NF:ntddk.IoSetHardErrorOrVerifyDevice
title: IoSetHardErrorOrVerifyDevice function
author: windows-driver-content
description: Lower-level drivers call the IoSetHardErrorOrVerifyDevice routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid.
old-location: kernel\iosetharderrororverifydevice.htm
old-project: kernel
ms.assetid: 67f41d3e-d306-400b-9970-88c62f0f7a7f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoSetHardErrorOrVerifyDevice, IoSetHardErrorOrVerifyDevice routine [Kernel-Mode Driver Architecture], k104_60c33e0c-64d3-404b-85a3-57e7da269404.xml, kernel.iosetharderrororverifydevice, ntddk/IoSetHardErrorOrVerifyDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoSetHardErrorOrVerifyDevice
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoSetHardErrorOrVerifyDevice function
Lower-level drivers call the <b>IoSetHardErrorOrVerifyDevice</b> routine to identify a removable media device that has encountered an error, so that a file system driver can prompt the user to verify that the medium is valid.

## Syntax

````
VOID IoSetHardErrorOrVerifyDevice(
  _In_ PIRP           Irp,
  _In_ PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`Irp`

Pointer to the IRP for which the driver encountered a user-induced error.

`DeviceObject`

Pointer to the target device to be verified for the I/O operation.


## Return Value

None

## Remarks

Lower-level drivers for removal media devices must call <b>IoSetHardErrorOrVerifyDevice</b> before completing an IRP, if a call to <a href="..\wdm\nf-wdm-ioiserroruserinduced.md">IoIsErrorUserInduced</a> returns <b>TRUE</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563916">Supporting Removable Media</a>.

Subsequently, a file system driver will use information supplied in the specified device object to send a dialog box to the user, who can correct the error and retry the operation or cancel it.

The IRP passed to <b>IoSetHardErrorOrVerifyDevice</b> must be associated with a thread. Therefore, before a driver calls <b>IoSetHardErrorOrVerifyDevice</b>, it must verify that <i>irp</i><b>-&gt;Tail.Overlay</b>.Thread is not <b>NULL</b>. If the value is <b>NULL</b>, <b>IoSetHardErrorOrVerifyDevice</b> must not be called using the current IRP. Instead, the driver should check all IRPs subsequently received and processed, until one is received for which <i>irp</i><b>-&gt;Tail.Overlay</b>.Thread is not <b>NULL</b>. At that point, <b>IoSetHardErrorOrVerifyDevice</b> can be called.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ntddk\nf-ntddk-ioraiseharderror.md">IoRaiseHardError</a>



<a href="..\wdm\nf-wdm-ioiserroruserinduced.md">IoIsErrorUserInduced</a>



<a href="..\ntddk\nf-ntddk-ioraiseinformationalharderror.md">IoRaiseInformationalHardError</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetHardErrorOrVerifyDevice routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>