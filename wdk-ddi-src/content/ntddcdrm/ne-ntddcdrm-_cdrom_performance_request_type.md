---
UID: NE:ntddcdrm._CDROM_PERFORMANCE_REQUEST_TYPE
title: "_CDROM_PERFORMANCE_REQUEST_TYPE"
author: windows-driver-content
description: The CDROM_PERFORMANCE_REQUEST_TYPE enumeration defines the types of performance data requests. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request.
old-location: storage\cdrom_performance_request_type.htm
old-project: storage
ms.assetid: 139D6E9A-36EE-4162-B9C5-12E9D57C7BE7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_PERFORMANCE_REQUEST_TYPE, CDROM_PERFORMANCE_REQUEST_TYPE, CDROM_PERFORMANCE_REQUEST_TYPE enumeration [Storage Devices], CdromPerformanceRequest, CdromWriteSpeedRequest, PCDROM_PERFORMANCE_REQUEST_TYPE, PCDROM_PERFORMANCE_REQUEST_TYPE enumeration pointer [Storage Devices], _CDROM_PERFORMANCE_REQUEST_TYPE, ntddcdrm/ CdromWriteSpeedRequest, ntddcdrm/CDROM_PERFORMANCE_REQUEST_TYPE, ntddcdrm/CdromPerformanceRequest, ntddcdrm/PCDROM_PERFORMANCE_REQUEST_TYPE, storage.cdrom_performance_request_type"
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
-	CDROM_PERFORMANCE_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: CDROM_PERFORMANCE_REQUEST_TYPE, *PCDROM_PERFORMANCE_REQUEST_TYPE
---

# _CDROM_PERFORMANCE_REQUEST_TYPE Enumeration
The CDROM_PERFORMANCE_REQUEST_TYPE enumeration defines the types of performance data requests. It is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request.

## Syntax
````
typedef enum _CDROM_PERFORMANCE_REQUEST_TYPE { 
  CdromPerformanceRequest   = 1,
   CdromWriteSpeedRequest   = 2
} CDROM_PERFORMANCE_REQUEST_TYPE, *PCDROM_PERFORMANCE_REQUEST_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>CdromPerformanceRequest</td>
                    <td>Requests streaming performance data.</td>
                </tr>
            
                <tr>
                    <td>CdromWriteSpeedRequest</td>
                    <td>Requests the  write speed descriptor.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>