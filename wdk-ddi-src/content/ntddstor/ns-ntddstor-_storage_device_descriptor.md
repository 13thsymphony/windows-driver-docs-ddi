---
UID: NS.NTDDSTOR._STORAGE_DEVICE_DESCRIPTOR
title: _STORAGE_DEVICE_DESCRIPTOR
author: windows-driver-content
description: The STORAGE_DEVICE_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage device descriptor data for a device.
old-location: storage\storage_device_descriptor.htm
old-project: storage
ms.assetid: 99b270a0-0634-41a8-9de7-d2a2d4c3059f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STORAGE_DEVICE_DESCRIPTOR, *PSTORAGE_DEVICE_DESCRIPTOR, STORAGE_DEVICE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DEVICE_DESCRIPTOR
req.alt-loc: ntddstor.h
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
---

# _STORAGE_DEVICE_DESCRIPTOR structure



## -description
The <b>STORAGE_DEVICE_DESCRIPTOR</b> structure 
   is used in conjunction with the 
   <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to 
   retrieve the storage device descriptor data for a device.


## -syntax

````
typedef struct _STORAGE_DEVICE_DESCRIPTOR {
  ULONG            Version;
  ULONG            Size;
  UCHAR            DeviceType;
  UCHAR            DeviceTypeModifier;
  BOOLEAN          RemovableMedia;
  BOOLEAN          CommandQueueing;
  ULONG            VendorIdOffset;
  ULONG            ProductIdOffset;
  ULONG            ProductRevisionOffset;
  ULONG            SerialNumberOffset;
  STORAGE_BUS_TYPE BusType;
  ULONG            RawPropertiesLength;
  UCHAR            RawDeviceProperties[1];
} STORAGE_DEVICE_DESCRIPTOR, *PSTORAGE_DEVICE_DESCRIPTOR;
````


## -struct-fields

### -field Version

Indicates the size of the 
      <b>STORAGE_DEVICE_DESCRIPTOR</b> structure. The 
      value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the descriptor in bytes, including ID strings which are appended to the 
      structure.

### -field DeviceType

Specifies the device type as defined by the Small Computer Systems Interface (SCSI) specification.

### -field DeviceTypeModifier

Specifies the device type modifier, if any, as defined by the SCSI specification. If no device type 
      modifier exists, this member is zero.

### -field RemovableMedia

Indicates when <b>TRUE</b> that the device's media (if any) is removable. If the device 
      has no media, this member should be ignored. When <b>FALSE</b> the device's media is not 
      removable.

### -field CommandQueueing

Indicates when <b>TRUE</b> that the device supports multiple outstanding commands (SCSI 
      tagged queuing or equivalent). When <b>FALSE</b>, the device does not support SCSI-tagged 
      queuing or the equivalent. The STORPORT driver is responsible for synchronizing the commands.

### -field VendorIdOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's vendor ID. If the device has no vendor ID, this member is zero.

### -field ProductIdOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's product ID. If the device has no product ID, this member is zero.

### -field ProductRevisionOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's product revision string. If the device has no product revision string, this member is 
      zero.

### -field SerialNumberOffset

Specifies the byte offset from the beginning of the structure to a <b>NULL</b>-terminated ASCII string that 
      contains the device's serial number. If the device has no serial number, this member is zero.

### -field BusType

Specifies an enumerator value of type 
      <a href="storage.storage_bus_type">STORAGE_BUS_TYPE</a> that indicates the type of bus to 
      which the device is connected. This should be used to interpret the raw device properties at the end of this 
      structure (if any).

### -field RawPropertiesLength

Indicates the number of bytes of bus-specific data that have been appended to this descriptor.

### -field RawDeviceProperties

Contains an array of length one that serves as a place holder for the first byte of the bus specific 
      property data.

## -remarks
Applications and storage class drivers issue a device-control request with the I/O control code 
     <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve 
     this structure, which contains information about a target device. The structure can be retrieved only from an 
     FDO; attempting to retrieve device properties from an adapter causes an error.

An application or driver can determine the required buffer size by casting the retrieved 
     <b>STORAGE_DEVICE_DESCRIPTOR</b> structure to a 
     <a href="storage.storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>, which contains 
     only <b>Version</b> and <b>Size</b>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>
</dt>
<dt>
<a href="storage.storage_adapter_descriptor">STORAGE_ADAPTER_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
<dt>
<a href="storage.storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>
</dt>
<dt>
<a href="storage.storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.storage_device_id_descriptor">STORAGE_DEVICE_ID_DESCRIPTOR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
