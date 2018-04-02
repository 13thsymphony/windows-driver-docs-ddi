---
UID: NS:wdm._BOOTDISK_INFORMATION_EX
title: "_BOOTDISK_INFORMATION_EX"
author: windows-driver-content
description: The BOOTDISK_INFORMATION_EX structure contains extended information describing the boot and system disks.
old-location: kernel\bootdisk_information_ex.htm
old-project: kernel
ms.assetid: c358220c-1e29-4889-b214-f2892c9ac47d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PBOOTDISK_INFORMATION_EX, BOOTDISK_INFORMATION_EX, BOOTDISK_INFORMATION_EX structure [Kernel-Mode Driver Architecture], PBOOTDISK_INFORMATION_EX, PBOOTDISK_INFORMATION_EX structure pointer [Kernel-Mode Driver Architecture], _BOOTDISK_INFORMATION_EX, kernel.bootdisk_information_ex, kstruct_a_abc410ed-6eca-4417-b428-565971e85287.xml, wdm/BOOTDISK_INFORMATION_EX, wdm/PBOOTDISK_INFORMATION_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	BOOTDISK_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: BOOTDISK_INFORMATION_EX, *PBOOTDISK_INFORMATION_EX
req.product: Windows 10 or later.
---

# _BOOTDISK_INFORMATION_EX structure
The <b>BOOTDISK_INFORMATION_EX</b> structure contains extended information describing the boot and system disks.

## Syntax
```
typedef struct _BOOTDISK_INFORMATION_EX {
  LONGLONG BootPartitionOffset;
  LONGLONG SystemPartitionOffset;
  ULONG    BootDeviceSignature;
  ULONG    SystemDeviceSignature;
  GUID     BootDeviceGuid;
  GUID     SystemDeviceGuid;
  BOOLEAN  BootDeviceIsGpt;
  BOOLEAN  SystemDeviceIsGpt;
} BOOTDISK_INFORMATION_EX, *PBOOTDISK_INFORMATION_EX;
```

## Members


`BootPartitionOffset`

Specifies the offset, in bytes, on the boot disk where the boot partition begins.

`SystemPartitionOffset`

Specifies the offset, in bytes, on the system disk where the system partition begins.

`BootDeviceSignature`

If the <b>BootDeviceIsGpt</b> member is <b>FALSE</b>, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.

`SystemDeviceSignature`

If the <b>SystemDeviceIsGpt</b> member is <b>FALSE</b>, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.

`BootDeviceGuid`

If the <b>BootDeviceIsGpt</b> member is <b>TRUE</b>, this specifies the GUID for the boot disk. Otherwise, this member is unused.

`SystemDeviceGuid`

If the <b>SystemDeviceIsGpt</b> member is <b>TRUE</b>, this specifies the GUID for the boot disk. Otherwise, this member is unused.

`BootDeviceIsGpt`

<b>TRUE</b> if the boot disk is formatted with the GPT partition table type.

`SystemDeviceIsGpt`

<b>TRUE</b> if the system disk is formatted with the GPT partition table type.

## Remarks
On Windows XP and later, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549153">IoGetBootDiskInformation</a> returns this structure to describe the boot and system disks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540652">BOOTDISK_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549153">IoGetBootDiskInformation</a>