---
UID: NS:storport._SCSI_PNP_REQUEST_BLOCK
title: "_SCSI_PNP_REQUEST_BLOCK"
author: windows-driver-content
description: TheSCSI_PNP_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for plug and play (PNP) requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsi_pnp_request_block.htm
old-project: storage
ms.assetid: 0627065b-62c2-4df8-973c-b4fb5811296e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_PNP_REQUEST_BLOCK, PSCSI_PNP_REQUEST_BLOCK, PSCSI_PNP_REQUEST_BLOCK structure pointer [Storage Devices], SCSI_PNP_REQUEST_BLOCK, SCSI_PNP_REQUEST_BLOCK structure [Storage Devices], StorFilterResourceRequirements, StorQueryCapabilities, StorQueryResourceRequirements, StorRemoveDevice, StorStartDevice, StorStopDevice, StorSupriseRemoval, _SCSI_PNP_REQUEST_BLOCK, storage.scsi_pnp_request_block, storport/PSCSI_PNP_REQUEST_BLOCK, storport/SCSI_PNP_REQUEST_BLOCK, structs-storport_d08ea849-f1d6-4584-b6a4-df7127f6873d.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Minitape.h, Srb.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	SCSI_PNP_REQUEST_BLOCK
product: Windows
targetos: Windows
req.typenames: SCSI_PNP_REQUEST_BLOCK, *PSCSI_PNP_REQUEST_BLOCK
req.product: Windows 10 or later.
---

# _SCSI_PNP_REQUEST_BLOCK structure
The<b>SCSI_PNP_REQUEST_BLOCK</b> structure is a special version of a <a href="..\minitape\ns-minitape-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> that is used for plug and play (PNP) requests.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
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

## Members


`_SCSI_REQUEST_BLOCK`



`DataBuffer`

Miniport driver should ignore this member.

`DataTransferLength`

Miniport driver should ignore this member.

`Function`

The operation to perform. For the <b>SCSI_PNP_REQUEST_BLOCK</b> structure, this member is always set to SRB_FUNCTION_PNP.

`Length`

The size, in bytes, of the <b>SCSI_PNP_REQUEST_BLOCK</b> structure.

`Lun`

The logical unit number (LUN) of the device.

`NextSrb`

Miniport driver should ignore this member.

`OriginalRequest`

Miniport driver should ignore this member.

`PathId`

The SCSI port or bus identifier for the request. This value is zero based.

`PnPAction`

The plug and play action to perform. This member can have one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="StorStartDevice"></a><a id="storstartdevice"></a><a id="STORSTARTDEVICE"></a><dl>
<dt><b>StorStartDevice</b></dt>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
Start the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorRemoveDevice"></a><a id="storremovedevice"></a><a id="STORREMOVEDEVICE"></a><dl>
<dt><b>StorRemoveDevice</b></dt>
<dt>0x02</dt>
</dl>
</td>
<td width="60%">
Remove the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorStopDevice"></a><a id="storstopdevice"></a><a id="STORSTOPDEVICE"></a><dl>
<dt><b>StorStopDevice</b></dt>
<dt>0x04</dt>
</dl>
</td>
<td width="60%">
Stop the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorQueryCapabilities"></a><a id="storquerycapabilities"></a><a id="STORQUERYCAPABILITIES"></a><dl>
<dt><b>StorQueryCapabilities</b></dt>
<dt>0x09</dt>
</dl>
</td>
<td width="60%">
Query the capabilities of the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorQueryResourceRequirements"></a><a id="storqueryresourcerequirements"></a><a id="STORQUERYRESOURCEREQUIREMENTS"></a><dl>
<dt><b>StorQueryResourceRequirements</b></dt>
<dt>0x0B</dt>
</dl>
</td>
<td width="60%">
Query the resource requirements for the device.

</td>
</tr>
<tr>
<td width="40%"><a id="StorFilterResourceRequirements"></a><a id="storfilterresourcerequirements"></a><a id="STORFILTERRESOURCEREQUIREMENTS"></a><dl>
<dt><b>StorFilterResourceRequirements</b></dt>
<dt>0x0D</dt>
</dl>
</td>
<td width="60%">
Filter the resource requirements for the device. 

</td>
</tr>
<tr>
<td width="40%"><a id="StorSupriseRemoval"></a><a id="storsupriseremoval"></a><a id="STORSUPRISEREMOVAL"></a><dl>
<dt><b>StorSupriseRemoval</b></dt>
<dt>0x17</dt>
</dl>
</td>
<td width="60%">
Surprise Removal of the device. This value was added in Windows 7.

</td>
</tr>
</table>

`PnPSubFunction`

This member is not currently used. Miniport drivers ignore this member.

`Reserved`

Reserved for system use.

`Reserved4`

Reserved for system use.

`SenseInfoBuffer`

Miniport driver should ignore this member.

`SrbExtension`

A pointer to the SRB extension. A miniport driver must not use this member if it set <b>SrbExtensionSize</b> to zero in the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure. The Storport driver does not initialize the memory that this member points to. The HBA can directly access the data that the miniport driver writes into the SRB extension. A miniport driver can obtain the physical address of the SRB extension by calling the <a href="..\storport\nf-storport-storportgetphysicaladdress.md">StorPortGetPhysicalAddress</a> routine.

`SrbFlags`

Miniport driver should ignore this member.

`SrbPnPFlags`

The PNP flags. Currently, the only flag allowed is SRB_PNP_FLAGS_ADAPTER_REQUEST, which indicates that the PNP request is for the adapter, and not for one of the devices on the adapter. If this flag is set, the miniport driver should ignore the values in the <b>PathId</b>, <b>TargetId</b>, and <b>Lun</b>.

`SrbStatus`

The status of the completed request. The miniport driver should set this value before notifying the Storport driver that the request has completed. A miniport driver notifies the Storport driver that the request has completed by calling the <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> routine with a notification type of <b>RequestComplete</b>. For a list of possible status values, see <a href="..\minitape\ns-minitape-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>.

`TargetId`

The target controller or device identifier on the bus.

`TimeOutValue`

The interval, in seconds, that the request can execute before the Storport driver determines that the request has timed out.

## Remarks
The Storport driver sends <b>SCSI_PNP_REQUEST_BLOCK</b> requests to a miniport driver to notify the miniport driver of Windows plug and play events that affect storage devices that are connected to the adapter.

The Storport driver calls <a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a> to pass SRBs to the miniport driver. <b>HwStorBuildIo</b> checks the <b>Function</b> member of the SRB to determine the type of the SRB. If the <b>Function</b> member is set to SRB_FUNCTION_PNP, the SRB is a structure of type <b>SCSI_PNP_REQUEST_BLOCK</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Storport.h, Minitape.h, Srb.h) |

## See Also

<a href="..\storport\nc-storport-hw_buildio.md">HwStorBuildIo</a>



<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>



<a href="..\minitape\ns-minitape-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_PNP_REQUEST_BLOCK structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>