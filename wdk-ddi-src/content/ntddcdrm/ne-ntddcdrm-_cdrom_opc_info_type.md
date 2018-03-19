---
UID: NE:ntddcdrm._CDROM_OPC_INFO_TYPE
title: "_CDROM_OPC_INFO_TYPE"
author: windows-driver-content
description: The CDROM_OPC_INFO_TYPE enumeration is a member of the CDROM_SIMPLE_OPC_INFO structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the IOCTL_CDROM_SEND_OPC_INFORMATION I/O control request.
old-location: storage\cdrom_opc_info_type.htm
old-project: storage
ms.assetid: 447D225C-4B73-4567-81E3-950EBC802F84
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_OPC_INFO_TYPE, CDROM_OPC_INFO_TYPE, CDROM_OPC_INFO_TYPE enumeration [Storage Devices], PCDROM_OPC_INFO_TYPE, PCDROM_OPC_INFO_TYPE enumeration pointer [Storage Devices], SimpleOpcInfo, _CDROM_OPC_INFO_TYPE, ntddcdrm/CDROM_OPC_INFO_TYPE, ntddcdrm/PCDROM_OPC_INFO_TYPE, ntddcdrm/SimpleOpcInfo, storage.cdrom_opc_info_type"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	Ntddcdrm.h
api_name:
-	CDROM_OPC_INFO_TYPE
product: Windows
targetos: Windows
req.typenames: CDROM_OPC_INFO_TYPE, *PCDROM_OPC_INFO_TYPE
---

# _CDROM_OPC_INFO_TYPE Enumeration
The <b>CDROM_OPC_INFO_TYPE</b>  enumeration is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a> structure. It defines the Optimum Power Calibration (OPC) request that is used as input to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a> I/O control request.

## Syntax
````
typedef enum _CDROM_OPC_INFO_TYPE { 
  SimpleOpcInfo  = 1
} CDROM_OPC_INFO_TYPE, *PCDROM_OPC_INFO_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>SimpleOpcInfo</td>
                    <td>Specifies the wrapper for the SEND OPC INFORMATION command from the Multimedia Commands (MMC) specification.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_send_opc_information.md">IOCTL_CDROM_SEND_OPC_INFORMATION</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_simple_opc_info.md">CDROM_SIMPLE_OPC_INFO</a>