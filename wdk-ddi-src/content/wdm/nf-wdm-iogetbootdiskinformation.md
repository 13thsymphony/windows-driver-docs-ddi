---
UID: NF:wdm.IoGetBootDiskInformation
title: IoGetBootDiskInformation function
author: windows-driver-content
description: The IoGetBootDiskInformation routine returns information describing the boot and system disks.
old-location: kernel\iogetbootdiskinformation.htm
old-project: kernel
ms.assetid: 744d5eae-2bdf-46b0-9412-f73e55939d8b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetBootDiskInformation
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
req.alt-api: IoGetBootDiskInformation
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetBootDiskInformation function



## -description
The <b>IoGetBootDiskInformation</b> routine returns information describing the boot and system disks.



## -syntax

````
NTSTATUS IoGetBootDiskInformation(
  _Inout_ PBOOTDISK_INFORMATION BootDiskInformation,
  _In_    ULONG                 Size
);
````


## -parameters

### -param BootDiskInformation [in, out]

Pointer to a caller-allocated buffer that the routine uses to return information about the boot and system disks. The routine fills this buffer in with either a <a href="..\wdm\ns-wdm-_bootdisk_information.md">BOOTDISK_INFORMATION</a> or a <a href="..\wdm\ns-wdm-_bootdisk_information_ex.md">BOOTDISK_INFORMATION_EX</a> structure.


### -param Size [in]

Specifies the size, in bytes, of the buffer specified by <i>BootDiskInformation</i>. Should be either <b>sizeof</b>(<b>BOOTDISK_INFORMATION</b>) or <b>sizeof</b>(<b>BOOTDISK_INFORMATION_EX</b>).


## -returns
<b>IoGetBootDiskInformation</b> returns one of the following status values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The routine successfully returned the requested information in the buffer specified by <i>BootDiskInformation</i>.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The value of <i>Size</i> is less than the size, in bytes, of a <b>BOOTDISK_INFORMATION</b> structure.
<dl>
<dt><b>STATUS_TOO_LATE</b></dt>
</dl>The driver called the routine after the system has already booted. Only boot and system drivers can call <b>IoGetBootDiskInformation</b>, and then only in their <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routines.

 


## -remarks
<b>IoGetBootDiskInformation</b> can be called only by a boot driver. This driver should call <b>IoGetBootDiskInformation</b> in a <a href="..\ntddk\nc-ntddk-driver_reinitialize.md">Reinitialize</a> callback routine that the driver registers by calling the <a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a> routine.

On Windows XP and later versions of Windows, if the <i>Size</i> parameter is <b>sizeof</b>(<b>BOOTDISK_INFORMATION_EX</b>) or larger, the routine returns a <a href="..\wdm\ns-wdm-_bootdisk_information_ex.md">BOOTDISK_INFORMATION_EX</a> structure in the <i>BootDiskInformation</i> buffer. Otherwise, if <i>Size</i> is at least <b>sizeof</b>(<b>BOOTDISK_INFORMATION</b>), the routine returns a <a href="..\wdm\ns-wdm-_bootdisk_information.md">BOOTDISK_INFORMATION</a> structure.

On Windows 2000, the routine returns only the <b>BOOTDISK_INFORMATION</b> structure.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_bootdisk_information.md">BOOTDISK_INFORMATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_bootdisk_information_ex.md">BOOTDISK_INFORMATION_EX</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioregisterbootdriverreinitialization.md">IoRegisterBootDriverReinitialization</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-driver_reinitialize.md">Reinitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetBootDiskInformation routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

