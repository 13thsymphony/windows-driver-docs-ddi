---
UID: NS.ntdddisk._DISK_CONTROLLER_NUMBER
title: DISK_CONTROLLER_NUMBER
author: windows-driver-content
description: DISK_CONTROLLER_NUMBER is used with IOCTL_DISK_CONTROLLER_NUMBER to retrieve the controller number and disk number of an IDE disk.
old-location: storage\disk_controller_number.htm
old-project: storage
ms.assetid: 5dc9f04b-8d7c-4ac7-9518-8836d56d5eed
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DISK_CONTROLLER_NUMBER, DISK_CONTROLLER_NUMBER, *PDISK_CONTROLLER_NUMBER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DISK_CONTROLLER_NUMBER
req.alt-loc: ntdddisk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# DISK_CONTROLLER_NUMBER structure



## -description
<p>DISK_CONTROLLER_NUMBER is used with IOCTL_DISK_CONTROLLER_NUMBER to retrieve the controller number and disk number of an IDE disk. </p>


## -syntax

````
typedef struct _DISK_CONTROLLER_NUMBER {
  ULONG ControllerNumber;
  ULONG DiskNumber;
} DISK_CONTROLLER_NUMBER, *PDISK_CONTROLLER_NUMBER;
````


## -struct-fields
<dl>

### -field <b>ControllerNumber</b>

<dd>
<p>Contains the number of the IDE controller for the disk.</p>
</dd>

### -field <b>DiskNumber</b>

<dd>
<p>Contains the number of the disk.</p>
</dd>
</dl>

## -remarks
<p>After DISK_CONTROLLER_NUMBER receives the controller number and the disk number, these values can be used to determine whether the disk is attached to the primary or to the secondary IDE controller. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h, Ntddk.h, or Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntdddisk\ni-ntdddisk-ioctl-disk-controller-number.md">IOCTL_DISK_CONTROLLER_NUMBER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_CONTROLLER_NUMBER structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
