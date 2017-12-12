---
UID: NS.WDM._VPB
title: _VPB
author: windows-driver-content
description: The volume parameter block (VPB) structure is used to map a device object that represents a mounted file system volume to a device object that represents a physical or virtual disk device.
old-location: ifsk\vpb.htm
old-project: ifsk
ms.assetid: aba1638f-1ab0-4953-afe9-1f539e5bd967
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _VPB, *PVPB, VPB
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VPB
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
req.product: Windows 10 or later.
---

# _VPB structure



## -description
The volume parameter block (VPB) structure is used to map a device object that represents a mounted file system volume to a device object that represents a physical or virtual disk device.



## -syntax

````
typedef struct _VPB {
  CSHORT                Size;
  CSHORT                Type;
  USHORT                Flags;
  USHORT                VolumeLabelLength;
  struct _DEVICE_OBJECT  *DeviceObject;
  struct _DEVICE_OBJECT  *RealDevice;
  ULONG                 SerialNumber;
  ULONG                 ReferenceCount;
  WCHAR                 VolumeLabel[MAXIMUM_VOLUME_LABEL_LENGTH / sizeof(WCHAR)];
} VPB, *PVPB;
````


## -struct-fields

### -field Size

A read-only member that is used by the system to indicate that the structure is a VPB object.


### -field Type

A read-only member that is used by the system to indicate that the structure is a VPB object.


### -field Flags

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field VPB_MOUNTED

</td>
<td width="60%">
This bit is set by the I/O manager to indicate that the file system has mounted the logical volume.

</td>
</tr>
<tr>

### -field VPB_LOCKED

</td>
<td width="60%">
This bit can be set or cleared by the file system driver that has mounted the logical volume. When set, the I/O manager will fail all subsequent create/open requests that are targeted at the logical volume. File systems may choose to set this member in response to application requests to lock the volume, or if they temporarily wish to prevent any create/open request from proceeding.

</td>
</tr>
<tr>

### -field VPB_PERSISTENT

</td>
<td width="60%">
This bit can be set or cleared by file system drivers. If set, the I/O manager will not delete the VPB structure even if <b>ReferenceCount</b> is zero.

</td>
</tr>
<tr>

### -field VPB_REMOVE_PENDING

</td>
<td width="60%">
Set by the Plug and Play (PnP) manager to indicate that the underlying device is being removed.

</td>
</tr>
<tr>

### -field VPB_RAW_MOUNT

</td>
<td width="60%">
Indicates that only the RAW file system can be mounted on the device.

</td>
</tr>
<tr>

### -field VPB_DIRECT_WRITES_ALLOWED

</td>
<td width="60%">
Indicates that direct write operations to the volume are allowed.  This flag is set either by the I/O manager when the RAW file system is mounted or by the file system itself when it determines that the volume can be safely written to. It is typically safe to write to a volume when the file system is dismounted.

</td>
</tr>
</table>
 


### -field VolumeLabelLength

A read/write member that specifies the length of the volume label, in bytes. This member must be set by the file system driver. If the volume has no label, this member must be set to zero.


### -field DeviceObject

A read/write member, set by the file system driver, which points to a device object of type <b>FILE_DEVICE_DISK_FILE_SYSTEM</b>. This device object is created by the file system driver to represent the mounted volume.


### -field RealDevice

A read-only member, set by the I/O manager, which points to the device object for a physical or virtual disk device that contains the mountable logical volume (pointed to by <b>DeviceObject</b>).


### -field SerialNumber

A read/write member that specifies the serial number associated with the file system volume.  This member should be set by the file system driver, if available.


### -field ReferenceCount

A read-only member that specifies the reference count for the VPB structure. If the reference count for the VPB structure is greater than zero, the I/O manager does not deallocate the VPB structure. Be aware that <b>ReferenceCount</b> can be considered a read/write member when a file system driver must keep the volume present to process a tear down request.


### -field VolumeLabel

A read/write member, set by the file system driver, that specifies the label of the mounted volume.  The length of the volume label must be 32 wide-characters or less. Currently <b>MAXIMUM_VOLUME_LABEL_LENGTH</b> is defined as follows:

<code>#define MAXIMUM_VOLUME_LABEL_LENGTH  (32 * sizeof(WCHAR));</code>


## -remarks
A volume parameter block (VPB) object is used to create an association between a physical disk device object and a logical volume device object. That is, a VPB maps a file system's volume device object to the device or partition upon which the volume is mounted. A VPB object exists only for device objects that represent physical media, virtual media, or logical media that can be mounted.

The I/O manager allocates and deallocates memory for the VPB structure from nonpaged pool. This allocation (or deallocation) occurs when a device object (as described previously) is created by calling either the <a href="kernel.iocreatedevice">IoCreateDevice</a> or <a href="ifsk.ioverifyvolume">IoVerifyVolume</a> functions. That is, the device object that is created must be one of the following types:<ul>
<li>FILE_DEVICE_DISK</li>
<li>FILE_DEVICE_CD_ROM</li>
<li>FILE_DEVICE_TAPE</li>
<li>FILE_DEVICE_VIRTUAL_DISK</li>
</ul>


For more information about device object types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.

Drivers must call <a href="ifsk.ioacquirevpbspinlock">IoAcquireVpbSpinLock</a> before they access any applicable members of the VPB object.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or FltKernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="ifsk.file_objectid_information">FILE_OBJECT</a>
</dt>
<dt>
<a href="ifsk.how_the_volume_is_mounted">How the Volume Is Mounted</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20VPB structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

