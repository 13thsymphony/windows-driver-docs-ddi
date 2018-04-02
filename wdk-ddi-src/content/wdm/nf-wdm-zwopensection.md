---
UID: NF:wdm.ZwOpenSection
title: ZwOpenSection function
author: windows-driver-content
description: The ZwOpenSection routine opens a handle for an existing section object.
old-location: kernel\zwopensection.htm
old-project: kernel
ms.assetid: c4373f7b-cc88-45da-a140-ead1c6891c11
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: NtOpenSection, ZwOpenSection, ZwOpenSection routine [Kernel-Mode Driver Architecture], k111_51851f81-8825-499b-9e7e-36faa8f53b23.xml, kernel.zwopensection, wdm/NtOpenSection, wdm/ZwOpenSection
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
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	ZwOpenSection
-	NtOpenSection
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ZwOpenSection function
The <b>ZwOpenSection</b> routine opens a handle for an existing <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">section object</a>.

## Syntax

```
NTSYSAPI NTSTATUS ZwOpenSection(
  PHANDLE            SectionHandle,
  ACCESS_MASK        DesiredAccess,
  POBJECT_ATTRIBUTES ObjectAttributes
);
```

## Parameters

`SectionHandle`

Pointer to a HANDLE variable that receives a handle to the section object.

`DesiredAccess`

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566428">ZwCreateSection</a>.

`ObjectAttributes`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


## Return Value

<b>ZwOpenSection</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure. Possible return values include:

## Remarks

If the section does not exist or the system did not grant the requested access, the operation fails.

Once the handle pointed to by <i>SectionHandle</i> is no longer in use, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtOpenSection</b>" instead of "<b>ZwOpenSection</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566428">ZwCreateSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566481">ZwMapViewOfSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567119">ZwUnmapViewOfSection</a>