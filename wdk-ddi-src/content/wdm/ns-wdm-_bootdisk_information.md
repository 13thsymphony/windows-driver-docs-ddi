---
UID: NS.WDM._BOOTDISK_INFORMATION
title: _BOOTDISK_INFORMATION
author: windows-driver-content
description: The BOOTDISK_INFORMATION structure contains basic information describing the boot and system disks.
old-location: kernel\bootdisk_information.htm
old-project: kernel
ms.assetid: dd2a525d-fb9d-4fea-b9d7-64b1f498550c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _BOOTDISK_INFORMATION, PBOOTDISK_INFORMATION, BOOTDISK_INFORMATION, *PBOOTDISK_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Drivers on Microsoft Windows XP and later versions of the Windows operating system should use the BOOTDISK_INFORMATION_EX structure instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BOOTDISK_INFORMATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _BOOTDISK_INFORMATION structure



## -description
The <b>BOOTDISK_INFORMATION</b> structure contains basic information describing the boot and system disks.



## -syntax

````
typedef struct _BOOTDISK_INFORMATION {
  LONGLONG BootPartitionOffset;
  LONGLONG SystemPartitionOffset;
  ULONG    BootDeviceSignature;
  ULONG    SystemDeviceSignature;
} BOOTDISK_INFORMATION, *PBOOTDISK_INFORMATION;
````


## -struct-fields

### -field BootPartitionOffset

Specifies the offset, in bytes, on the boot disk where the boot partition begins.


### -field SystemPartitionOffset

Specifies the offset, in bytes, on the system disk where the system partition begins.


### -field BootDeviceSignature

If the boot disk is formatted with an MBR partition table, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.


### -field SystemDeviceSignature

If the system disk is formatted with an MBR partition table, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.


## -remarks

<a href="kernel.iogetbootdiskinformation">IoGetBootDiskInformation</a> returns this structure to describe the boot and system disks.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Drivers on Microsoft Windows XP and later versions of the Windows operating system should use the <a href="kernel.bootdisk_information_ex">BOOTDISK_INFORMATION_EX</a> structure instead.

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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iogetbootdiskinformation">IoGetBootDiskInformation</a>
</dt>
<dt>
<a href="kernel.bootdisk_information_ex">BOOTDISK_INFORMATION_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BOOTDISK_INFORMATION structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

