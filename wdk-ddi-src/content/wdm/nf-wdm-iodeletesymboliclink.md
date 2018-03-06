---
UID: NF:wdm.IoDeleteSymbolicLink
title: IoDeleteSymbolicLink function
author: windows-driver-content
description: The IoDeleteSymbolicLink routine removes a symbolic link from the system.
old-location: kernel\iodeletesymboliclink.htm
old-project: kernel
ms.assetid: 68ad19a5-4694-4b75-8062-75b06bdc16ed
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoDeleteSymbolicLink, IoDeleteSymbolicLink routine [Kernel-Mode Driver Architecture], k104_6ff2f570-3573-4d12-b338-cca69515ef1a.xml, kernel.iodeletesymboliclink, wdm/IoDeleteSymbolicLink
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
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
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
-	IoDeleteSymbolicLink
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoDeleteSymbolicLink function
The <b>IoDeleteSymbolicLink</b> routine removes a symbolic link from the system.

## Syntax

````
NTSTATUS IoDeleteSymbolicLink(
  _In_ PUNICODE_STRING SymbolicLinkName
);
````

## Parameters

`SymbolicLinkName`

Pointer to a buffered Unicode string that is the user-visible name for the symbolic link.


## Return Value

<b>IoDeleteSymbolicLink</b> returns STATUS_SUCCESS if the symbolic link object is deleted.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\ntddk\nf-ntddk-iodeassignarcname.md">IoDeassignArcName</a>



<a href="..\wdm\nf-wdm-iocreateunprotectedsymboliclink.md">IoCreateUnprotectedSymbolicLink</a>



<a href="..\wdm\nf-wdm-iocreatesymboliclink.md">IoCreateSymbolicLink</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoDeleteSymbolicLink routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>