---
UID: NS.STORPORT._SCSI_POWER_REQUEST_BLOCK
title: _SCSI_POWER_REQUEST_BLOCK
author: windows-driver-content
description: The SCSI_POWER_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for power management requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsi_power_request_block.htm
old-project: storage
ms.assetid: 04981b68-db32-461b-b24b-8b2bf2e53f78
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _SCSI_POWER_REQUEST_BLOCK, SCSI_POWER_REQUEST_BLOCK, *PSCSI_POWER_REQUEST_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_POWER_REQUEST_BLOCK
req.alt-loc: storport.h
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
req.product: Windows 10 or later.
---

# _SCSI_POWER_REQUEST_BLOCK structure



## -description
The <b>SCSI_POWER_REQUEST_BLOCK</b> structure is a special version of a <a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a> that is used for power management requests.


## -syntax

````
typedef struct _SCSI_POWER_REQUEST_BLOCK {
  USHORT                     Length;
  UCHAR                      Function;
  UCHAR                      SrbStatus;
  UCHAR                      SrbPowerFlags;
  UCHAR                      PathId;
  UCHAR                      TargetId;
  UCHAR                      Lun;
  STOR_DEVICE_POWER_STATE    DevicePowerState;
  ULONG                      SrbFlags;
  ULONG                      DataTransferLength;
  ULONG                      TimeOutValue;
  PVOID                      DataBuffer;
  PVOID                      SenseInfoBuffer;
  struct _SCSI_REQUEST_BLOCK  *NextSrb;
  PVOID                      OriginalRequest;
  PVOID                      SrbExtension;
  STOR_POWER_ACTION          PowerAction;
#ifdef _WIN64
  ULONG                      Reserved;
#endif 
  UCHAR                      Reserved5[16];
} SCSI_POWER_REQUEST_BLOCK, *PSCSI_POWER_REQUEST_BLOCK;
````


## -struct-fields

### -field Length

The size, in bytes, of the <b>SCSI_POWER_REQUEST_BLOCK</b> structure.

### -field Function

The operation to perform. For the <b>SCSI_POWER_REQUEST_BLOCK</b> structure, this member is always set to SRB_FUNCTION_POWER.

### -field SrbStatus

The status of the completed request. This member should be set by the miniport driver before it notifies the Storport driver that the request has completed. A miniport driver notifies the Storport driver that the request has completed by calling the <a href="storage.storportnotification">StorPortNotification</a> function with the <a href="storage.storportnotification__notificationtype___requestcomplete_">RequestComplete</a> notification type.
See <a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a> in the WDK documentation for a list of possible values for this member.

### -field SrbPowerFlags

The power management flags. Currently, the only flag allowed is SRB_POWER_FLAGS_ADAPTER_REQUEST, which indicates that the power management request is for the adapter. If this flag is set, the miniport driver should ignore the values in the <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>.  

### -field PathId

The SCSI port or bus identifier for the request. This value is zero based.

### -field TargetId

The target controller or device identifier on the bus.

### -field Lun

The logical unit number (LUN) of the device.

### -field DevicePowerState

An enumerator value of type <a href="storage.stor_device_power_state">STOR_DEVICE_POWER_STATE</a> that specifies the requested power state of the device.

### -field SrbFlags

Miniport driver should ignore this member.

### -field DataTransferLength

Miniport driver should ignore this member.

### -field TimeOutValue

The interval, in seconds, that the request can execute before the Storport driver determines that the request has timed out.

### -field DataBuffer

Miniport driver should ignore this member.

### -field SenseInfoBuffer

Miniport driver should ignore this member.

### -field NextSrb

Miniport driver should ignore this member.

### -field OriginalRequest

Miniport driver should ignore this member.

### -field SrbExtension

A pointer to the SRB extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the <a href="storage.hw_initialization_data__storport_">HW_INITIALIZATION_DATA</a> structure. The Storport driver does not initialize the memory that this member points to. The HBA can directly access the data that the miniport driver writes into the SRB extension. A miniport driver can obtain the physical address of the SRB extension by calling the <a href="storage.storportgetphysicaladdress">StorPortGetPhysicalAddress</a> routine. 

### -field PowerAction

An enumerator value of type <a href="storage.stor_power_action">STOR_POWER_ACTION</a> that specifies the type of system shutdown that is about to occur. This value is meaningful only if the device is moving into the D1, D2, or D3 power state as indicated by the <b>DevicePowerState</b> member. 

### -field Reserved

Reserved for system use.

### -field Reserved5

Reserved for system use.

## -remarks
The Storport driver calls <a href="storage.hwstorbuildio">HwStorBuildIo</a> to pass SRBs to the miniport driver. <b>HwStorBuildIo</b> should check the <b>Function</b> member of the SRB to determine the type of the SRB. If the <b>Function</b> member is set to SRB_FUNCTION_POWER, the SRB is a structure of type <b>SCSI_POWER_REQUEST_BLOCK</b>.

The Storport driver sends <b>SCSI_POWER_REQUEST_BLOCK</b> requests to a miniport driver to notify the miniport driver of Windows power events that affect storage devices that are connected to the adapter. In the case of a power up event, this request gives the miniport driver an opportunity to initialize itself. In the case of a hibernation or shutdown event, this request gives the miniport driver an opportunity to complete I/O requests and prepare for a power down. The miniport driver can use the value in the <b>PowerAction</b> member of the <b>SCSI_POWER_REQUEST_BLOCK</b> to determine what actions are required. After the miniport driver completes the <b>SCSI_POWER_REQUEST_BLOCK</b> request, the Storport driver calls <a href="storage.hwscsiadaptercontrol">HwScsiAdapterControl</a> with a control request of <b>ScsiStopAdapter</b> to power down the adapter. The miniport driver reinitialize while processing the SRB_FUNCTION_POWER request, or it can wait and reinitialize when the Storport driver calls <a href="storage.hwstoradaptercontrol">HwStorAdapterControl</a> to perform a an <b>ScsiRestartAdapter</b> control request.

 When transitioning from the D0 power state to a lower-powered state (D1, D2, or D3) the Storport driver sends a <b>SCSI_POWER_REQUEST_BLOCK</b> request to the miniport driver before the underlying bus driver powers down the adapter. 

The following conditions must exist before the Storport driver will send a <b>SCSI_POWER_REQUEST_BLOCK</b> request to the miniport driver:

The adapter is not stopped.

The I/O queue for the adapter is paused.

The adapter hardware is powered up.

The miniport can access the adapter's hardware resources.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hwstorbuildio">HwStorBuildIo</a>
</dt>
<dt>
<a href="storage.scsi_request_block">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="storage.storportnotification">StorPortNotification</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_POWER_REQUEST_BLOCK structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
