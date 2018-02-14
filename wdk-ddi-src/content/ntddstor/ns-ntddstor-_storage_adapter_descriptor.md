---
UID: NS:ntddstor._STORAGE_ADAPTER_DESCRIPTOR
title: "_STORAGE_ADAPTER_DESCRIPTOR"
author: windows-driver-content
description: The STORAGE_ADAPTER_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the storage adapter descriptor data for a device.
old-location: storage\storage_adapter_descriptor.htm
old-project: storage
ms.assetid: 83ef2a1a-f95e-4b05-8911-e5e900192630
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: STORAGE_ADAPTER_DESCRIPTOR structure [Storage Devices], SRB_TYPE_STORAGE_REQUEST_BLOCK, storage.storage_adapter_descriptor, ntddstor/STORAGE_ADAPTER_DESCRIPTOR, structs-general_196c7640-0a2d-4567-8958-1244c46b84a6.xml, PSTORAGE_ADAPTER_DESCRIPTOR, ntddstor/PSTORAGE_ADAPTER_DESCRIPTOR, SRB_TYPE_SCSI_REQUEST_BLOCK, STORAGE_ADDRESS_TYPE_BTL8, _STORAGE_ADAPTER_DESCRIPTOR, PSTORAGE_ADAPTER_DESCRIPTOR structure pointer [Storage Devices], STORAGE_ADAPTER_DESCRIPTOR
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_ADAPTER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: STORAGE_ADAPTER_DESCRIPTOR, PSTORAGE_ADAPTER_DESCRIPTOR
---

# _STORAGE_ADAPTER_DESCRIPTOR structure
The <b>STORAGE_ADAPTER_DESCRIPTOR</b> structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the storage adapter descriptor data for a device.

## Syntax
````
typedef struct _STORAGE_ADAPTER_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  ULONG   MaximumTransferLength;
  ULONG   MaximumPhysicalPages;
  ULONG   AlignmentMask;
  BOOLEAN AdapterUsesPio;
  BOOLEAN AdapterScansDown;
  BOOLEAN CommandQueueing;
  BOOLEAN AcceleratedTransfer;
  UCHAR   BusType;
  USHORT  BusMajorVersion;
  USHORT  BusMinorVersion;
  UCHAR   SrbType;
  UCHAR   AddressType;
} STORAGE_ADAPTER_DESCRIPTOR, *PSTORAGE_ADAPTER_DESCRIPTOR;
````

## Members


`AcceleratedTransfer`

Indicates when <b>TRUE</b> that the HBA supports synchronous transfers as a way of speeding up I/O. When <b>FALSE</b>, the HBA does not support synchronous transfers as a way of speeding up I/O.

`AdapterScansDown`

Indicates when <b>TRUE</b> that the HBA scans down for BIOS devices, that is, the HBA begins scanning with the highest device number rather than the lowest. When <b>FALSE</b>, the HBA begins scanning with the lowest device number. This member is reserved for legacy miniport drivers.

`AdapterUsesPio`

Indicates when <b>TRUE</b> that the HBA uses Programmed Input/Output (PIO) and requires the use of system-space virtual addresses mapped to physical memory for data buffers. When <b>FALSE</b>, the HBA does not use PIO.

`AddressType`

Specifies the address type of the HBA.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ADDRESS_TYPE_BTL8"></a><a id="storage_address_type_btl8"></a><dl>
<dt><b>STORAGE_ADDRESS_TYPE_BTL8</b></dt>
</dl>
</td>
<td width="60%">
The HBA uses 8-bit bus, target, and LUN addressing.

</td>
</tr>
</table>
 

This member is valid starting with Windows 8.

`AlignmentMask`

Specifies the HBA's alignment requirements for transfers. A storage class driver sets the <b>AlignmentRequirement</b> field in its device objects to this value. The alignment mask indicates alignment restrictions for buffers required by the HBA for transfer operations. The valid mask values are 0 (byte aligned), 1 (word aligned), 3 (DWORD aligned), and 7 (double DWORD aligned).

`BusMajorVersion`

Specifies the major version number, if any, of the HBA.

`BusMinorVersion`

Specifies the minor version number, if any, of the HBA.

`CommandQueueing`

Indicates when <b>TRUE</b> that the HBA supports SCSI-tagged queuing and/or per-logical-unit internal queues, or the non-SCSI equivalent. When <b>FALSE</b>, the HBA neither supports SCSI-tagged queuing nor per-logical-unit internal queues.

`MaximumPhysicalPages`

Specifies the maximum number of discontinuous physical pages the HBA can manage in a single transfer (in other words, the extent of its scatter/gather support).

`MaximumTransferLength`

Specifies the maximum number of bytes the host bus adapter (HBA) can transfer in a single operation.

`Size`

Specifies the total size of the descriptor, in bytes.

`SrbType`

Specifies the SCSI request block (SRB) type used by the HBA.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SRB_TYPE_SCSI_REQUEST_BLOCK"></a><a id="srb_type_scsi_request_block"></a><dl>
<dt><b>SRB_TYPE_SCSI_REQUEST_BLOCK</b></dt>
</dl>
</td>
<td width="60%">
The HBA uses SCSI request blocks.

</td>
</tr>
<tr>
<td width="40%"><a id="SRB_TYPE_STORAGE_REQUEST_BLOCK"></a><a id="srb_type_storage_request_block"></a><dl>
<dt><b>SRB_TYPE_STORAGE_REQUEST_BLOCK</b></dt>
</dl>
</td>
<td width="60%">
The HBA uses extended SCSI request blocks.

</td>
</tr>
</table>
 

This member is valid starting with Windows 8.

`Version`

Contains the version of the structure <b>STORAGE_ADAPTER_DESCRIPTOR</b>. The value of this member will change as members are added to the structure.

## Remarks
Storage class drivers issue a device-control request with the I/O control code <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> to retrieve this structure, which contains configuration information from the HBA for data transfer operations. The structure can be retrieved either from the device object for the bus or from a functional device object (FDO), which forwards the request to the underlying bus.

If excessive protocol errors occur on an HBA that supports synchronous transfers (<b>AcceleratedTransfer</b> is <b>TRUE</b>), the storage class driver can disable synchronous transfers by setting SRB_FLAGS_DISABLE_SYNCH_TRANSFER in SRBs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ns-ntddstor-_storage_adapter_descriptor.md">STORAGE_ADAPTER_DESCRIPTOR</a>



<a href="..\ntddstor\ns-ntddstor-_storage_device_descriptor.md">STORAGE_DEVICE_DESCRIPTOR</a>



<a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>



<a href="..\ntddstor\ns-ntddstor-_storage_descriptor_header.md">STORAGE_DESCRIPTOR_HEADER</a>



<a href="..\ntddstor\ns-ntddstor-_storage_device_id_descriptor.md">STORAGE_DEVICE_ID_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_ADAPTER_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>