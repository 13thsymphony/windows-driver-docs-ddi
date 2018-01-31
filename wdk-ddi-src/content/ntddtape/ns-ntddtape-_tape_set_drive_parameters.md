---
UID : NS:ntddtape._TAPE_SET_DRIVE_PARAMETERS
title : "_TAPE_SET_DRIVE_PARAMETERS"
author : windows-driver-content
description : The TAPE_SET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_SET_DRIVE_PARAMS request to adjust the configurable parameters of a tape drive.
old-location : storage\tape_set_drive_parameters.htm
old-project : storage
ms.assetid : 87317972-b0df-4691-a9a5-bd0bbc150e53
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.tape_set_drive_parameters, ntddtape/PTAPE_SET_DRIVE_PARAMETERS, *PTAPE_SET_DRIVE_PARAMETERS, ntddtape/TAPE_SET_DRIVE_PARAMETERS, PTAPE_SET_DRIVE_PARAMETERS structure pointer [Storage Devices], structs-tape_621b7e53-4f98-4fad-9f75-28420dc78031.xml, TAPE_SET_DRIVE_PARAMETERS structure [Storage Devices], PTAPE_SET_DRIVE_PARAMETERS, _TAPE_SET_DRIVE_PARAMETERS, TAPE_SET_DRIVE_PARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddtape.h
req.include-header : Ntddtape.h
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
req.typenames : "*PTAPE_SET_DRIVE_PARAMETERS, TAPE_SET_DRIVE_PARAMETERS"
---

# _TAPE_SET_DRIVE_PARAMETERS structure
The TAPE_SET_DRIVE_PARAMETERS structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_drive_params.md">IOCTL_TAPE_SET_DRIVE_PARAMS</a> request to adjust the configurable parameters of a tape drive.

## Syntax
````
typedef struct _TAPE_SET_DRIVE_PARAMETERS {
  BOOLEAN ECC;
  BOOLEAN Compression;
  BOOLEAN DataPadding;
  BOOLEAN ReportSetmarks;
  ULONG   EOTWarningZoneSize;
} TAPE_SET_DRIVE_PARAMETERS, *PTAPE_SET_DRIVE_PARAMETERS;
````

## Members


`Compression`

When set to <b>TRUE</b>, instructs the device to compress data prior to writing it. If a drive must be at beginning of partition before it can set compression (TAPE_DRIVE_SET_CMP_BOP_ONLY), the caller is responsible for positioning the drive before attempting to set compression. When <b>FALSE</b>, the device does not compress data prior to writing it.

`DataPadding`

When set to <b>TRUE</b>, instructs the device to pad data with zeros. This is to keep the tape streaming until data is ready. When <b>FALSE</b>, the device does not pad data with zeros.

`ECC`

When set to <b>TRUE</b>, instructs the device to use hardware error correction. When <b>FALSE</b>, the device does not use hardware error correction.

`EOTWarningZoneSize`

Indicates the size in bytes of the early warning zone toward the end of the tape in which the drive returns a check condition when it enters the zone.

`ReportSetmarks`

When set to <b>TRUE</b>, instructs the device to report setmarks encountered during read or space operations. When <b>FALSE</b>, the device does not report setmarks encountered during read or space operations.

## Remarks
The miniclass driver can ignore parameters its device does not support. The calling application is responsible for determining whether a device supports a particular feature before attempting to set it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddtape.h (include Ntddtape.h) |

## See Also

<a href="..\ntddtape\ni-ntddtape-ioctl_tape_set_drive_params.md">IOCTL_TAPE_SET_DRIVE_PARAMS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567952">TapeMiniSetDriveParameters</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_SET_DRIVE_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>