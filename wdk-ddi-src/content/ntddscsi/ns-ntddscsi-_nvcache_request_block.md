---
UID: NS:ntddscsi._NVCACHE_REQUEST_BLOCK
title: _NVCACHE_REQUEST_BLOCK
author: windows-driver-content
description: The NVCACHE_REQUEST_BLOCK structure is used in conjunction with the IOCTL_SCSI_MINIPORT request to manage hybrid-hard disk drive (H-HDD) devices (for example, Microsoft ReadyDrive technology).
old-location: storage\nvcache_request_block.htm
old-project: storage
ms.assetid: 25ca2d81-72a5-47ae-bdfd-0ec63e1ca39a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _NVCACHE_REQUEST_BLOCK, NVCACHE_REQUEST_BLOCK, *PNVCACHE_REQUEST_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NVCACHE_REQUEST_BLOCK
req.alt-loc: ntddscsi.h
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
req.typenames: NVCACHE_REQUEST_BLOCK, *PNVCACHE_REQUEST_BLOCK
---

# _NVCACHE_REQUEST_BLOCK structure



## -description
The <b>NVCACHE_REQUEST_BLOCK</b> structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a> request to manage hybrid-hard disk drive (H-HDD) devices (for example, Microsoft ReadyDrive technology). This topic defines the general structure for both input data and output data for a call made to the NV Cache Manager. A caller should fill all required fields before calling <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> or <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a>. The miniport driver must do the same after the requested function is completed, and before it returns.



## -syntax

````
typedef struct _NVCACHE_REQUEST_BLOCK {
  ULONG     NRBSize;
  USHORT    Function;
  ULONG     NRBFlags;
  ULONG     NRBStatus;
  ULONG     Count;
  ULONGLONG LBA;
  ULONG     DataBufSize;
  ULONG     NVCacheStatus;
  ULONG     NVCacheSubStatus;
} NVCACHE_REQUEST_BLOCK, *PNVCACHE_REQUEST_BLOCK;
````


## -struct-fields

### -field NRBSize

The <b>sizeof</b>(NVCACHE_REQUEST_BLOCK).


### -field Function

Specifies the operation to be performed, which can be one of the following values:




### -field NRB_FUNCTION_NVCACHE_INFO

Get NV Cache Manager feature support information from the device. Upon the successful completion of this function, the required data fields are returned to the caller. The return data structure is <a href="..\ntddscsi\ns-ntddscsi-_nv_feature_parameter.md">NV_FEATURE_PARAMETER</a>.


### -field NRB_FUNCTION_SPINDLE_STATUS

Determine if the device is currently spinning up or spinning down. For an ATA device, a Check Power Mode command is required to obtain the device's spindle status. For a SCSI device, a Mode Sense command can be used to query the device's current power mode.


### -field NRB_FUNCTION_NVCACHE_POWER_MODE_SET

Turn on the NV Cache Manager power mode.


### -field NRB_FUNCTION_NVCACHE_POWER_MODE_RESET

Turn off the NV Cache Manager power mode.


### -field NRB_FUNCTION_FLUSH_NVCACHE

Flush the data that is currently pinned in NV cache memory to make the required NV cache memory space available.


### -field NRB_FUNCTION_QUERY_PINNED_SET

Get the Logical Block Address (LBA) ranges currently in the NV Cache Manager pinned set.


### -field NRB_FUNCTION_QUERY_CACHE_MISS

Request that the device report NV Cache Misses in LBA ranges in a single 512-byte block.


### -field NRB_FUNCTION_ADD_LBAS_PINNED_SET

Add the LBAs that are specified in the NV Cache Manager Set Data to the NV Cache Manager Pinned Set if they are not already.


### -field NRB_FUNCTION_REMOVE_LBAS_PINNED_SET

Remove the LBAs that are specified in the NV Cache Set Data from the NV Cache pinned set.


### -field NRB_FUNCTION_QUERY_HYBRID_DISK_STATUS

Reserved for future use.


### -field NRB_FUNCTION_PASS_HINT_PAYLOAD

Pass IO hints to a SATA device.

</dd>
</dl>

### -field NRBFlags

Reserved for future use.


### -field NRBStatus

Indicates the NV Cache Manager function request status from the driver. There are seven possible values for this field:




### -field NRB_SUCCESS

No error.


### -field NRB_ILLEGAL_REQUEST

Illegal request detected by the port driver.


### -field NRB_INVALID_PARAMETER

Invalid parameter passed to the port driver.


### -field NRB_INPUT_DATA_OVERRUN

Too much data provided to the port driver.


### -field NRB_INPUT_DATA_UNDERRUN

Not enough data provided to the port driver.


### -field NRB_OUTPUT_DATA_OVERRUN

Too much data returned from the port driver.


### -field NRB_OUTPUT_DATA_UNDERRUN

Not enough data returned from the port driver.

</dd>
</dl>

### -field Count

Number of 512-byte blocks to be transferred with the specified function.


### -field LBA

Starting LBA of the device for the specified function.


### -field DataBufSize

Size of the data buffer, in bytes.


### -field NVCacheStatus

Status returned from the device. For an ATA device, this value is the contents of the Status Register in its Task File. For a SCSI device, this value is the Sense Code returned from the device.


### -field NVCacheSubStatus

The error code returned from the device. For an ATA device, this value is the contents of the Error Register in its Task File. For a SCSI device, this value is the Sense key returned from the device.


## -remarks
For more information on function behavior, see section 7.20 of the <a href="http://go.microsoft.com/fwlink/p/?linkid=74996">ATA8-ACS specification</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h (include Ntddscsi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport.md">IOCTL_SCSI_MINIPORT</a>
</dt>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_nvcache.md">IOCTL_SCSI_MINIPORT_NVCACHE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20NVCACHE_REQUEST_BLOCK structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

