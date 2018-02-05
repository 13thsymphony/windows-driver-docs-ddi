---
UID : NS:storport._SCSI_WMI_REQUEST_BLOCK
title : "_SCSI_WMI_REQUEST_BLOCK"
author : windows-driver-content
description : This structure is a special version of a SCSI_REQUEST_BLOCK for use with WMI commands.
old-location : storage\scsi_wmi_request_block.htm
old-project : storage
ms.assetid : 6dc10c3a-b47e-42c3-a209-34977fb219f1
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PSCSI_WMI_REQUEST_BLOCK, storage.scsi_wmi_request_block, _SCSI_WMI_REQUEST_BLOCK, *PSCSI_WMI_REQUEST_BLOCK, SCSI_WMI_REQUEST_BLOCK structure [Storage Devices], srb/PSCSI_WMI_REQUEST_BLOCK, structs-scsibus_6188bca6-990b-4471-b8ea-2cd5b2b27d51.xml, SCSI_WMI_REQUEST_BLOCK, PSCSI_WMI_REQUEST_BLOCK structure pointer [Storage Devices], srb/SCSI_WMI_REQUEST_BLOCK
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : storport.h
req.include-header : Storport.h, Srb.h, Storport.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SCSI_WMI_REQUEST_BLOCK, *PSCSI_WMI_REQUEST_BLOCK
req.product : Windows 10 or later.
---

# _SCSI_WMI_REQUEST_BLOCK structure
This structure is a special version of a <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> for use with WMI commands. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SCSI_WMI_REQUEST_BLOCK {
  USHORT Length;
  UCHAR  Function;
  UCHAR  SrbStatus;
  UCHAR  WMISubFunction;
  UCHAR  PathId;
  UCHAR  TargetId;
  UCHAR  Lun;
  UCHAR  Reserved1;
  UCHAR  WMIFlags;
  UCHAR  Reserved2[2];
  ULONG  SrbFlags;
  ULONG  DataTransferLength;
  ULONG  TimeOutValue;
  PVOID  DataBuffer;
  PVOID  DataPath;
  PVOID  Reserved3;
  PVOID  OriginalRequest;
  PVOID  SrbExtension;
  ULONG  Reserved4;
#ifdef _WIN64
  ULONG  Reserved6;
#endif 
  UCHAR  Reserved5[16];
} SCSI_WMI_REQUEST_BLOCK, *PSCSI_WMI_REQUEST_BLOCK;
````

## Members


`DataBuffer`

Points to the data buffer. A miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with <i>Buffer</i> set to this value. Miniport drivers can use this value as a data pointer regardless of the value of <b>MapBuffers</b> in the PORT_CONFIGURATION_INFORMATION for the HBA. A miniport driver cannot transfer data directly into the buffer using DMA.

`DataPath`

Specifies the WMI data path for this request. A miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with <i>DataPath</i> set to this value.

`DataTransferLength`

Indicates the size in bytes of the data buffer. A miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with <i>BufferSize</i> set to this value. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred.

`Function`

SRB_FUNCTION_WMI, which specifies that the request is a WMI request. If this member is not set to SRB_FUNCTION_WMI, the miniport driver should fail the request.

`Length`

Specifies the size in bytes of this structure.

`Lun`

Indicates the logical unit number of the device. If SRB_WMI_FLAGS_ADAPTER_REQUEST is set in <b>WMIFlags</b>, this member is reserved.

`OriginalRequest`

Points to the IRP for this request. This member is irrelevant to miniport drivers.

`PathId`

Indicates the SCSI port or bus for the request. This value is zero-based. If SRB_WMI_FLAGS_ADAPTER_REQUEST is set in <b>WMIFlags</b>, this member is reserved.

`Reserved1`

Reserved for system use and not available for use by miniport drivers.

`Reserved2`

Reserved for system use and not available for use by miniport drivers.

`Reserved3`

Reserved for system use and not available for use by miniport drivers.

`Reserved4`

Reserved for system use and not available for use by miniport drivers.

`Reserved5`

Reserved for system use and not available for use by miniport drivers.

`Reserved6`

Reserved for system use and not available for use by miniport drivers. This member is valid starting with Windows Server 2003 with SP1.

`SrbExtension`

Points to the Srb extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the HW_INITIALIZATION_DATA. The memory at <b>SrbExtension</b> is not initialized by the OS-specific port driver, and the miniport driver-determined data can be accessed directly by the HBA. The corresponding physical address can be obtained by calling <a href="..\srb\nf-srb-scsiportgetphysicaladdress.md">ScsiPortGetPhysicalAddress</a> with the <b>SrbExtension</b> pointer.

`SrbFlags`

Indicates various parameters and options about the request. <b>SrbFlags</b> is read-only. This member will be set to one or more of the following flags ORed together:












#### SRB_FLAGS_DATA_IN

Indicates data will be transferred from the device to the system.


#### SRB_FLAGS_DATA_OUT

Indicates data will be transferred from the system to the device.


#### SRB_FLAGS_DISABLE_DISCONNECT

Indicates the HBA should not allow the target to disconnect from the SCSI bus during processing of this request.


#### SRB_FLAGS_DISABLE_SYNCH_TRANSFER

Indicates the HBA, if possible, should perform asynchronous I/O for this transfer request. If synchronous I/O was negotiated previously, the HBA must renegotiate for asynchronous I/O before performing the transfer.


#### SRB_FLAGS_NO_DATA_TRANSFER

Indicates no data transfer with this request. If this is set, the flags SRB_FLAGS_DATA_OUT, SRB_FLAGS_DATA_IN, and SRB_FLAGS_UNSPECIFIED_DIRECTION are clear.

`SrbStatus`

Returns the status of the completed request. This member should be set by the miniport driver before it notifies the OS-specific driver that the request has completed by calling <a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a> with <b>RequestComplete</b>. The value of this member can be any value listed for <b>SrbStatus</b> in SCSI_REQUEST_BLOCK.

`TargetId`

Indicates the target controller or device on the bus. If SRB_WMI_FLAGS_ADAPTER_REQUEST is set in <b>WMIFlags</b>, this member is reserved.

`TimeOutValue`

Indicates the interval in seconds that the request can execute before the OS-specific port driver might consider it timed out. Miniport drivers are not required to time requests because the port driver already does.

`WMIFlags`

Indicates that the WMI request is for the adapter if SRB_WMI_FLAGS_ADAPTER_REQUEST is set and that <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b> are reserved. Otherwise, <b>WMIFlags</b> will be <b>NULL</b>, indicating that the request is for the device specified by <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>.

`WMISubFunction`

Indicates the WMI action to be performed. A miniport driver calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with <i>MinorFunction</i> set to this value. The subfunction value corresponds to the WMI minor IRP number that identifies the WMI operation.

## Remarks
Windows NT storage class and filter drivers can send WMI SRBs to the system port driver. The system port driver will handle certain WMI requests on behalf of miniport drivers. If the port driver cannot handle a WMI request, it forwards the request to the miniport driver. 

A miniport driver receives WMI requests from the port driver only if the miniport driver set <b>WmiDataProvider</b> in the PORT_CONFIGURATION_INFORMATION structure. If the miniport driver supports a request, it should process it and complete the request by calling <b>ScsiPortNotification</b> twice, first with <b>RequestComplete</b> and then with <b>NextRequest</b> (or <b>NextLuRequest</b>). 

For information about supporting WMI in miniport drivers, see the <a href="https://msdn.microsoft.com/5c2ed322-0fc9-4004-9a5f-f4d3c6a59fe9">Windows Management Instrumentation</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Storport.h, Srb.h, Storport.h) |

## See Also

<a href="..\srb\nf-srb-scsiportnotification.md">ScsiPortNotification</a>

<a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION (SCSI)</a>

<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>

<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_WMI_REQUEST_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>