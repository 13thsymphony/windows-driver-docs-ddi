---
UID: NS:wdm._BOOTDISK_INFORMATION_EX
title: _BOOTDISK_INFORMATION_EX
author: windows-driver-content
description: The BOOTDISK_INFORMATION_EX structure contains extended information describing the boot and system disks.
old-location: kernel\bootdisk_information_ex.htm
old-project: kernel
ms.assetid: c358220c-1e29-4889-b214-f2892c9ac47d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _BOOTDISK_INFORMATION_EX, *PBOOTDISK_INFORMATION_EX, BOOTDISK_INFORMATION_EX
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
req.alt-api: BOOTDISK_INFORMATION_EX
req.alt-loc: wdm.h
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
req.typenames: *PBOOTDISK_INFORMATION_EX, BOOTDISK_INFORMATION_EX
req.product: Windows 10 or later.
---

# _BOOTDISK_INFORMATION_EX structure



## -description
The <b>BOOTDISK_INFORMATION_EX</b> structure contains extended information describing the boot and system disks.



## -syntax

````
typedef struct _BOOTDISK_INFORMATION_EX {
  LONGLONG BootPartitionOffset;
  LONGLONG SystemPartitionOffset;
  ULONG    BootDeviceSignature;
  ULONG    SystemDeviceSignature;
  GUID     BootDeviceGuid;
  GUID     SystemDeviceGuid;
  BOOLEAN  BootDeviceIsGpt;
  BOOLEAN  SystemDeviceIsGpt;
} BOOTDISK_INFORMATION_EX, *PBOOTDISK_INFORMATION_EX;
````


## -struct-fields

### -field BootPartitionOffset

Specifies the offset, in bytes, on the boot disk where the boot partition begins.


### -field SystemPartitionOffset

Specifies the offset, in bytes, on the system disk where the system partition begins.


### -field BootDeviceSignature

If the <b>BootDeviceIsGpt</b> member is <b>FALSE</b>, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.


### -field SystemDeviceSignature

If the <b>SystemDeviceIsGpt</b> member is <b>FALSE</b>, this specifies the signature for the disk's MBR partition table. Otherwise, this member is unused.


### -field BootDeviceGuid

If the <b>BootDeviceIsGpt</b> member is <b>TRUE</b>, this specifies the GUID for the boot disk. Otherwise, this member is unused. 


### -field SystemDeviceGuid

If the <b>SystemDeviceIsGpt</b> member is <b>TRUE</b>, this specifies the GUID for the boot disk. Otherwise, this member is unused. 


### -field BootDeviceIsGpt

<b>TRUE</b> if the boot disk is formatted with the GPT partition table type.


### -field SystemDeviceIsGpt

<b>TRUE</b> if the system disk is formatted with the GPT partition table type. 


## -remarks
On Windows XP and later, <a href="..\wdm\nf-wdm-iogetbootdiskinformation.md">IoGetBootDiskInformation</a> returns this structure to describe the boot and system disks.


## -requirements
<table>
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
<a href="..\wdm\nf-wdm-iogetbootdiskinformation.md">IoGetBootDiskInformation</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_bootdisk_information.md">BOOTDISK_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20BOOTDISK_INFORMATION_EX structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

