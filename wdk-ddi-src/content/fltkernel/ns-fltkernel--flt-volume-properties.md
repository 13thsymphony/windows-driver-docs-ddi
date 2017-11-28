---
UID: NS.fltkernel._FLT_VOLUME_PROPERTIES
title: FLT_VOLUME_PROPERTIES
author: windows-driver-content
description: The FLT_VOLUME_PROPERTIES structure is passed as a parameter to FltGetVolumeProperties.
old-location: ifsk\flt_volume_properties.htm
old-project: ifsk
ms.assetid: e7be6cb6-a59d-4244-ba36-e7d5b36b1416
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FLT_VOLUME_PROPERTIES, FLT_VOLUME_PROPERTIES, *PFLT_VOLUME_PROPERTIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FLT_VOLUME_PROPERTIES
req.alt-loc: fltkernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# FLT_VOLUME_PROPERTIES structure



## -description
<p>The FLT_VOLUME_PROPERTIES structure is passed as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. </p>


## -syntax

````
typedef struct _FLT_VOLUME_PROPERTIES {
  DEVICE_TYPE    DeviceType;
  ULONG          DeviceCharacteristics;
  ULONG          DeviceObjectFlags;
  ULONG          AlignmentRequirement;
  USHORT         SectorSize;
  USHORT         Flags;
  UNICODE_STRING FileSystemDriverName;
  UNICODE_STRING FileSystemDeviceName;
  UNICODE_STRING RealDeviceName;
} FLT_VOLUME_PROPERTIES, *PFLT_VOLUME_PROPERTIES;
````


## -struct-fields
<dl>

### -field <b>DeviceType</b>

<dd>
<p>Receives the device type of the volume. Must be a valid storage device type, such as one of the following values defined in ntifs.h: </p>
<dl>
<dd>
<p>FILE_DEVICE_CD_ROM</p>
</dd>
<dd>
<p>FILE_DEVICE_DISK</p>
</dd>
<dd>
<p>FILE_DEVICE_DVD</p>
</dd>
<dd>
<p>FILE_DEVICE_MASS_STORAGE</p>
</dd>
<dd>
<p>FILE_DEVICE_NETWORK</p>
</dd>
<dd>
<p>FILE_DEVICE_VIRTUAL_DISK</p>
</dd>
</dl>
<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>. </p>
</dd>

### -field <b>DeviceCharacteristics</b>

<dd>
<p>Receives the device characteristics of the volume. For more information, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>. </p>
</dd>

### -field <b>DeviceObjectFlags</b>

<dd>
<p>Receives the device object flags for the volume. For more information about these flags, see the reference entries for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>. </p>
</dd>

### -field <b>AlignmentRequirement</b>

<dd>
<p>Receives the buffer alignment required by the underlying device. The value must be one of the FILE_<i>xxxx</i>_ALIGNMENT values defined in ntifs.h. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. </p>
</dd>

### -field <b>SectorSize</b>

<dd>
<p>Receives the volume sector size, in bytes. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Provides additional description of the volume. This member can be zero or one of the following flags. In versions prior to Windows 10, version 1607, this member was named <b>Reserved0</b> and reserved for system use.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VOL_PROP_FL_DAX_VOLUME"></a><a id="vol_prop_fl_dax_volume"></a><dl>

### -field <b>VOL_PROP_FL_DAX_VOLUME</b>

</dl>
</td>
<td width="60%">
<p>This flag indicates that the volume is a direct access (DAX) volume.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>FileSystemDriverName</b>

<dd>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that receives the service name of the file system that is mounted on this volume. The buffer for this Unicode string is contiguous with this structure and does not need to be initialized before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. </p>
</dd>

### -field <b>FileSystemDeviceName</b>

<dd>
<p>UNICODE_STRING structure that receives the name of the file system device object associated with this volume. The buffer for this Unicode string is contiguous with this structure and does not need to be initialized before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. </p>
</dd>

### -field <b>RealDeviceName</b>

<dd>
<p>UNICODE_STRING structure that receives the name of the storage device object associated with this volume. This structure is empty for network file systems. The buffer for this Unicode string is contiguous with this structure and does not need to be initialized before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. </p>
</dd>
</dl>

## -remarks
<p>Storage for the FLT_VOLUME_PROPERTIES structure is typically allocated from paged pool. </p>

<p>To get the volume name for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543249">FltGetVolumeName</a>. </p>

<p>To get the volume globally unique identifier (GUID) name for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543230">FltGetVolumeGuidName</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543249">FltGetVolumeName</a>
</dt>
<dt><b>FltGetVolumeName</b></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_VOLUME_PROPERTIES structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
