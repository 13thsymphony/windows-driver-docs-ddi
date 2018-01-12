---
UID: NS:irb._IDE_DEVICE_PARAMETERS
title: _IDE_DEVICE_PARAMETERS
author: windows-driver-content
description: The IDE_DEVICE_PARAMETERS structure contains configuration information that the port driver provides to the miniport driver to configure a device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_device_parameters.htm
old-project: storage
ms.assetid: e2b908ce-df40-4d64-b8fd-77da18b4f6bd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _IDE_DEVICE_PARAMETERS, *PIDE_DEVICE_PARAMETERS, IDE_DEVICE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDE_DEVICE_PARAMETERS
req.alt-loc: irb.h
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
req.typenames: *PIDE_DEVICE_PARAMETERS, IDE_DEVICE_PARAMETERS
---

# _IDE_DEVICE_PARAMETERS structure



## -description
The IDE_DEVICE_PARAMETERS structure contains configuration information that the port driver provides to the miniport driver to configure a device.



## -syntax

````
typedef struct _IDE_DEVICE_PARAMETERS {
  USHORT                  Version;
  IDE_DEVICE_TYPE         IdeDeviceType;
  UCHAR                   TargetId;
  UCHAR                   MaximumLun;
  UCHAR                   NumberOfOverlappedRequests;
  UCHAR                   MaxBlockXfer;
  USHORT                  DeviceCharacteristics;
  ATA_ADDRESS_TRANSLATION AddressTranslation;
  union {
    LARGE_INTEGER MaxLba;
    struct {
      USHORT NumCylinders;
      USHORT NumHeads;
      USHORT NumSectorsPerTrack;
      USHORT Reserved;
    } Chs;
  };
  ULONG                   BytesPerLogicalSector;
  ULONG                   BytesPerPhysicalSector;
  ULONG                   BytesOffsetForSectorAlignment;
  ULONG                   TransferModeSupported;
  ULONG                   TransferModeSelected;
} IDE_DEVICE_PARAMETERS, *PIDE_DEVICE_PARAMETERS;
````


## -struct-fields

### -field Version

Indicates the size of the <i>Device</i> parameters structure. The miniport driver should verify that sizeof(IDE_DEVICE_PARAMETERS) is less than or equal to the <b>Version</b> field.


### -field IdeDeviceType

Indicates the type of the device. The allowed device types are <i>DeviceIsAta</i> for ATA devices, <i>DeviceIsAtapi</i> for ATAPI devices, and <i>DeviceNotExist</i> if no device was found at that address. The other fields in this structure are not valid if the <b>IdeDeviceType</b> is set to <i>DeviceNotExist</i>.


### -field TargetId

Specifies the target ID of the device.


### -field MaximumLun

The miniport driver must update this field to indicate the maximum logical unit number supported by this device. By default, the member is set to 0 indicating the existence of just one LUN.


### -field NumberOfOverlappedRequests

The miniport driver must update this field to specify the number of overlapped requests it can handle for this device. By default, the member is set to 1.


### -field MaxBlockXfer

Specifies the number of sectors in a block of data to be transferred. This value applies to the data blocks used in ATA block transfer commands such as Read Multiple (0xC4), Write Multiple (0xC5). For more information about the ReadMultiple and WriteMultiple commands, see the <i>ATA Specification</i>.


### -field DeviceCharacteristics

Specifies the device characteristics. The table below lists the characteristics that could be set in this member. The high byte of this member is opaque and shall not be changed by the ATA miniport.

<table>
<tr>
<th>Device Characteristic</th>
<th>Description</th>
</tr>
<tr>
<td>
DFLAGS_REMOVABLE_MEDIA

</td>
<td>
Indicates that the drive has removable media

</td>
</tr>
<tr>
<td>
DFLAGS_ REMOVABLE_DEVICE

</td>
<td>
Indicates that the device can be safely unplugged

</td>
</tr>
<tr>
<td>
DFLAGS_FUA_SUPPORT

</td>
<td>
Indicates that the device supports FUA (Force Unit Access)

</td>
</tr>
<tr>
<td>
DFLAGS_INT_DRQ

</td>
<td>
Indicates that the device interrupts as DRQ is set after receiving ATAPI Packet command

</td>
</tr>
<tr>
<td>
DFLAGS_MSN_SUPPORT

</td>
<td>
Indicates that the device supports Media Status Notification.

</td>
</tr>
</table>
 


### -field AddressTranslation

Contains an enumeration value of type <a href="..\irb\ne-irb-ata_address_translation.md">ATA_ADDRESS_TRANSLATION</a> that specifies the sort of address translation used during data transfers.


### -field MaxLba

Specifies the maximum user-addressable logical block address (LBA). This member is defined when <b>AddressTranslation</b> is equal to either <b>LbaMode</b> or <b>Lba48BitMode</b>.


### -field Chs

Specifies the drive geometry with the values for the number of cylinders, heads per cylinder, and the sectors per track. This member is defined when <b>AddressTranslation</b> is equal to <b>ChsMode</b>.


### -field BytesPerLogicalSector

This member specifies the number of bytes per logical sector (LBA) for the given device.


### -field BytesPerPhysicalSector

This member specifies the number of bytes per physical sector (that is, the smallest amount of data that the device can physically write internally) for the given device.


### -field BytesOffsetForSectorAlignment

This member specifies the location of sector 0 within the first physical sector as defined in the ATA specification represented in bytes.


### -field TransferModeSupported

Contains a bitmap that indicates the supported transfer modes.


### -field TransferModeSelected

Indicates the selected transfer modes on the device. The miniport driver must set this member.


## -remarks
The port driver passes a IDE_DEVICE_PARAMETERS structure to the miniport driver when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff557467">IdeHwInitialize</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Irb.h (include Irb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\irb\ne-irb-ide_device_type.md">IDE_DEVICE_TYPE</a>
</dt>
<dt>
<a href="..\irb\ne-irb-ata_address_translation.md">ATA_ADDRESS_TRANSLATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557467">IdeHwInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_DEVICE_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

