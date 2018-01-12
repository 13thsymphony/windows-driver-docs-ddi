---
UID: NS:storport._SCSI_PNP_REQUEST_BLOCK
title: _SCSI_PNP_REQUEST_BLOCK
author: windows-driver-content
description: TheSCSI_PNP_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for plug and play (PNP) requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsi_pnp_request_block.htm
old-project: storage
ms.assetid: 0627065b-62c2-4df8-973c-b4fb5811296e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SCSI_PNP_REQUEST_BLOCK, *PSCSI_PNP_REQUEST_BLOCK, SCSI_PNP_REQUEST_BLOCK
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
req.alt-api: SCSI_PNP_REQUEST_BLOCK
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
req.typenames: *PSCSI_PNP_REQUEST_BLOCK, SCSI_PNP_REQUEST_BLOCK
req.product: Windows 10 or later.
---

# _SCSI_PNP_REQUEST_BLOCK structure



## -description
The<b>SCSI_PNP_REQUEST_BLOCK</b> structure is a special version of a <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> that is used for plug and play (PNP) requests.



## -syntax

````
typedef struct _SCSI_PNP_REQUEST_BLOCK {
  USHORT                     Length;
  UCHAR                      Function;
  UCHAR                      SrbStatus;
  UCHAR                      PnPSubFunction;
  UCHAR                      PathId;
  UCHAR                      TargetId;
  UCHAR                      Lun;
  STOR_PNP_ACTION            PnPAction;
  ULONG                      SrbFlags;
  ULONG                      DataTransferLength;
  ULONG                      TimeOutValue;
  PVOID                      DataBuffer;
  PVOID                      SenseInfoBuffer;
  struct _SCSI_REQUEST_BLOCK  *NextSrb;
  PVOID                      OriginalRequest;
  PVOID                      SrbExtension;
  ULONG                      SrbPnPFlags;
#ifdef _WIN64
  ULONG                      Reserved;
#endif 
  UCHAR                      Reserved4[16];
} SCSI_PNP_REQUEST_BLOCK, *PSCSI_PNP_REQUEST_BLOCK;
````


## -struct-fields

### -field Length

The size, in bytes, of the <b>SCSI_PNP_REQUEST_BLOCK</b> structure. 


### -field Function

The operation to perform. For the <b>SCSI_PNP_REQUEST_BLOCK</b> structure, this member is always set to SRB_FUNCTION_PNP. 


### -field SrbStatus

The status of the completed request. The miniport driver should set this value before notifying the Storport driver that the request has completed. A miniport driver notifies the Storport driver that the request has completed by calling the <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> routine with a notification type of <b>RequestComplete</b>. For a list of possible status values, see <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>.  


### -field PnPSubFunction

This member is not currently used. Miniport drivers ignore this member. 


### -field PathId

The SCSI port or bus identifier for the request. This value is zero based. 


### -field TargetId

The target controller or device identifier on the bus. 


### -field Lun

The logical unit number (LUN) of the device. 


### -field PnPAction

The plug and play action to perform. This member can have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field StorStartDevice
### -field 0x00

</td>
<td width="60%">
Start the device.

</td>
</tr>
<tr>

### -field StorRemoveDevice
### -field 0x02

</td>
<td width="60%">
Remove the device.

</td>
</tr>
<tr>

### -field StorStopDevice
### -field 0x04

</td>
<td width="60%">
Stop the device.

</td>
</tr>
<tr>

### -field StorQueryCapabilities
### -field 0x09

</td>
<td width="60%">
Query the capabilities of the device.

</td>
</tr>
<tr>

### -field StorQueryResourceRequirements
### -field 0x0B

</td>
<td width="60%">
Query the resource requirements for the device.

</td>
</tr>
<tr>

### -field StorFilterResourceRequirements
### -field 0x0D

</td>
<td width="60%">
Filter the resource requirements for the device. 

</td>
</tr>
<tr>

### -field StorSupriseRemoval
### -field 0x17

</td>
<td width="60%">
Surprise Removal of the device. This value was added in Windows 7.

</td>
</tr>
</table>
 


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

A pointer to the SRB extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. The Storport driver does not initialize the memory that this member points to. The HBA can directly access the data that the miniport driver writes into the SRB extension. A miniport driver can obtain the physical address of the SRB extension by calling the <a href="..\storport\nf-storport-storportgetphysicaladdress.md">StorPortGetPhysicalAddress</a> routine. 


### -field SrbPnPFlags

The PNP flags. Currently, the only flag allowed is SRB_PNP_FLAGS_ADAPTER_REQUEST, which indicates that the PNP request is for the adapter, and not for one of the devices on the adapter. If this flag is set, the miniport driver should ignore the values in the <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>.


### -field Reserved

Reserved for system use.


### -field Reserved4

Reserved for system use.


## -remarks
The Storport driver sends <b>SCSI_PNP_REQUEST_BLOCK</b> requests to a miniport driver to notify the miniport driver of Windows plug and play events that affect storage devices that are connected to the adapter.

The Storport driver calls <a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a> to pass SRBs to the miniport driver. <b>HwStorBuildIo</b> checks the <b>Function</b> member of the SRB to determine the type of the SRB. If the <b>Function</b> member is set to SRB_FUNCTION_PNP, the SRB is a structure of type <b>SCSI_PNP_REQUEST_BLOCK</b>.


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
<a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_PNP_REQUEST_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

