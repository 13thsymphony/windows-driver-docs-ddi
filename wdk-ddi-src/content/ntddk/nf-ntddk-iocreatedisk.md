---
UID: NF:ntddk.IoCreateDisk
title: IoCreateDisk function
author: windows-driver-content
description: The IoCreateDisk routine initializes a raw disk by creating a new partition table.
old-location: storage\iocreatedisk.htm
old-project: storage
ms.assetid: 0ad85551-a8d2-4f7f-958b-fe23111de340
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IoCreateDisk
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: This routine is only available on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCreateDisk
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
req.irql: 
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# IoCreateDisk function



## -description
The <b>IoCreateDisk</b> routine initializes a raw disk by creating a new partition table.



## -syntax

````
NTSTATUS IoCreateDisk(
  _In_     PDEVICE_OBJECT      DeviceObject,
  _In_opt_ struct _CREATE_DISK *Disk
);
````


## -parameters

### -param DeviceObject [in]

Specifies the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> for the raw disk.


### -param Disk [in, optional]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552484">CREATE_DISK</a> structure that specifies the type and parameters for the partition table. If <i>Disk</i> is <b>NULL</b>, the routine deletes the partition table on the disk.


## -returns
Returns STATUS_SUCCESS on success, or the appropriate error code on failure.


## -remarks
<b>IoCreateDisk</b> must only be used by disk drivers. Other drivers should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559436">IOCTL_DISK_CREATE_DISK</a> I/O request instead.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552484">CREATE_DISK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559436">IOCTL_DISK_CREATE_DISK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IoCreateDisk routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

