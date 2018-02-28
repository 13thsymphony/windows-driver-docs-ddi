---
UID: NF:ntddk.ZwAllocateLocallyUniqueId
title: ZwAllocateLocallyUniqueId function
author: windows-driver-content
description: The ZwAllocateLocallyUniqueId routine allocates a locally unique identifier (LUID).
old-location: kernel\zwallocatelocallyuniqueid.htm
old-project: kernel
ms.assetid: 63ca0e60-700b-459a-a88a-bc7bb6f5f6e6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtAllocateLocallyUniqueId, ZwAllocateLocallyUniqueId, ZwAllocateLocallyUniqueId routine [Kernel-Mode Driver Architecture], k111_de9ec26c-4aa4-4f1b-b876-c6e27bb2a067.xml, kernel.zwallocatelocallyuniqueid, ntddk/NtAllocateLocallyUniqueId, ntddk/ZwAllocateLocallyUniqueId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
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
-	ZwAllocateLocallyUniqueId
-	NtAllocateLocallyUniqueId
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# ZwAllocateLocallyUniqueId function
The <b>ZwAllocateLocallyUniqueId</b> routine allocates a locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>).

## Syntax

````
NTSTATUS ZwAllocateLocallyUniqueId(
  _Out_ PLUID LUID
);
````

## Parameters

`Luid`

TBD


## Return Value

<b>ZwAllocateLocallyUniqueId </b>returns STATUS_SUCCESS if the operation succeeds or the appropriate NTSTATUS value if the operation fails. If the output parameter cannot be written to, the routine returns STATUS_ACCESS_VIOLATION.

## Remarks

The allocated <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a> is unique to the local system only, and uniqueness is guaranteed only until the system is next restarted.

<div class="alert"><b>Note</b>  If the call to the <b>ZwAllocateLocallyUniqueId</b> function occurs in user mode, you should use the name "<b>NtAllocateLocallyUniqueId</b>" instead of "<b>ZwAllocateLocallyUniqueId</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo |

## See Also

<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwAllocateLocallyUniqueId routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>