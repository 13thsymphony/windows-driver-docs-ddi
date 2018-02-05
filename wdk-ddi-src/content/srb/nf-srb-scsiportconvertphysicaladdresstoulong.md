---
UID : NF:srb.ScsiPortConvertPhysicalAddressToUlong
title : ScsiPortConvertPhysicalAddressToUlong function
author : windows-driver-content
description : The ScsiPortConvertPhysicalAddressToUlong routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location : storage\scsiportconvertphysicaladdresstoulong.htm
old-project : storage
ms.assetid : 55c258d2-922a-430a-ba6b-b05a078b712d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.scsiportconvertphysicaladdresstoulong, ScsiPortConvertPhysicalAddressToUlong, srb/ScsiPortConvertPhysicalAddressToUlong, scsiprt_5417817d-81ab-4ba9-96f6-589991aecfce.xml, ScsiPortConvertPhysicalAddressToUlong routine [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : srb.h
req.include-header : Miniport.h, Scsi.h
req.target-type : Desktop
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
req.lib : Scsiport.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product : Windows 10 or later.
---


# ScsiPortConvertPhysicalAddressToUlong function
The <b>ScsiPortConvertPhysicalAddressToUlong</b> routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
ULONG ScsiPortConvertPhysicalAddressToUlong(
  _In_ SCSI_PHYSICAL_ADDRESS Address
);
````

## Parameters

`Address`

Specifies a value of type SCSI_PHYSICAL_ADDRESS.


## Return Value

<b>ScsiPortConvertPhysicalAddressToUlong</b> returns the low-order part of the given SCSI_PHYSICAL_ADDRESS value. A miniport driver cannot call this routine to truncate a 64-bit physical address. Such addresses should be used as quadword values, which contain all 64 bits.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportgetphysicaladdress.md">ScsiPortGetPhysicalAddress</a>

<a href="..\srb\ns-srb-_access_range.md">ACCESS_RANGE</a>

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortConvertPhysicalAddressToUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>