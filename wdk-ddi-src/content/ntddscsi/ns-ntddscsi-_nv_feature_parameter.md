---
UID : NS:ntddscsi._NV_FEATURE_PARAMETER
title : "_NV_FEATURE_PARAMETER"
author : windows-driver-content
description : The NV_FEATURE_PARAMETER structure is used in conjunction with the IOCTL_SCSI_MINIPORT_NVCACHE request to get NV Cache Manager feature support information from the device.
old-location : storage\nv_feature_parameter.htm
old-project : storage
ms.assetid : 06b07b50-577c-4762-aea6-38bd1ada8973
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ntddscsi/PNV_FEATURE_PARAMETER, PNV_FEATURE_PARAMETER, NV_FEATURE_PARAMETER structure [Storage Devices], NV_FEATURE_PARAMETER, _NV_FEATURE_PARAMETER, *PNV_FEATURE_PARAMETER, PNV_FEATURE_PARAMETER structure pointer [Storage Devices], structs-nvcache_ac844d4b-783b-4248-8699-353eef5a3d52.xml, storage.nv_feature_parameter, ntddscsi/NV_FEATURE_PARAMETER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddscsi.h
req.include-header : Ntddscsi.h
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
req.typenames : NV_FEATURE_PARAMETER, *PNV_FEATURE_PARAMETER
---

# _NV_FEATURE_PARAMETER structure
The NV_FEATURE_PARAMETER structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_nvcache.md">IOCTL_SCSI_MINIPORT_NVCACHE</a> request to get NV Cache Manager feature support information from the device. The NV Cache Manager feature parameters structure is returned by the miniport driver upon the successful return from the NRB_NVCACHE_INFO function, as requested in the Function field of the <a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a> structure.

The values in these fields come from the IDENTIFY DEVICE command in section 7.16 of the <a href="http://go.microsoft.com/fwlink/p/?linkid=74996">ATA8-ACS specification</a>.

## Syntax
````
typedef struct _NV_FEATURE_PARAMETER {
  USHORT NVPowerModeEnabled;
  USHORT NVParameterReserv1;
  USHORT NVCmdEnabled;
  USHORT NVParameterReserv2;
  USHORT NVPowerModeVer;
  USHORT NVCmdVer;
  ULONG  NVSize;
  USHORT NVReadSpeed;
  USHORT NVWrtSpeed;
  ULONG  DeviceSpinUpTime;
} NV_FEATURE_PARAMETER, *PNV_FEATURE_PARAMETER;
````

## Members


`DeviceSpinUpTime`

Taken from word 219, bits 0 through 7 of the IDENTIFY DEVICE data, this field contains the device's estimated time to spin up, in seconds.

`NVCmdEnabled`

Taken from word 214, bit 4 of the IDENTIFY DEVICE data, a value of one means the NV Cache feature set is enabled.

`NVCmdVer`

Taken from word 214, bits 12 through 15 of the IDENTIFY DEVICE data, this field contains the NV Cache feature set version.

`NVParameterReserv1`

Reserved for future use.

`NVParameterReserv2`

Reserved for future use.

`NVPowerModeEnabled`

Taken from word 214, bit 0 of the IDENTIFY DEVICE data, a value of one means the NV Cache Power Mode feature set is enabled.

`NVPowerModeVer`

Taken from word 214, bits 8 through 11 of the IDENTIFY DEVICE data, this field contains the NV Cache Power Mode feature set version.

`NVReadSpeed`

Taken from word 217 of the IDENTIFY DEVICE data, this field contains the NV Cache Read Transfer Speed, in megabytes per second (MB/s).

`NVSize`

Taken from words 215 and 216 of the IDENTIFY DEVICE data, this field contains the NV Cache Size, in logical blocks.

`NVWrtSpeed`

Taken from word 218 of the IDENTIFY DEVICE data, this field contains the NV Cache Write Transfer Speed, in megabytes per second (MB/s).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ns-ntddscsi-_nvcache_request_block.md">NVCACHE_REQUEST_BLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20NV_FEATURE_PARAMETER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>