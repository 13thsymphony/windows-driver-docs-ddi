---
UID: NS:pointofservicedriverinterface._MSR_AUTHENTICATE_DEVICE
title: "_MSR_AUTHENTICATE_DEVICE"
author: windows-driver-content
description: This structure provides the authentication information used to authenticate a device.
old-location: pos\msr_authenticate_device.htm
old-project: pos
ms.assetid: b75dce2c-5ad5-4340-b1b7-5fcf4440e58c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PMSR_AUTHENTICATE_DEVICE, MSR_AUTHENTICATE_DEVICE, MSR_AUTHENTICATE_DEVICE structure, PMSR_AUTHENTICATE_DEVICE, PMSR_AUTHENTICATE_DEVICE structure pointer, _MSR_AUTHENTICATE_DEVICE, pointofservicedriverinterface/MSR_AUTHENTICATE_DEVICE, pointofservicedriverinterface/PMSR_AUTHENTICATE_DEVICE, pos.msr_authenticate_device"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
api_name:
-	MSR_AUTHENTICATE_DEVICE
product: Windows
targetos: Windows
req.typenames: MSR_AUTHENTICATE_DEVICE, *PMSR_AUTHENTICATE_DEVICE
---

# _MSR_AUTHENTICATE_DEVICE structure
This structure provides the authentication information used to authenticate a device.

## Syntax
```
typedef struct _MSR_AUTHENTICATE_DEVICE {
  unsigned char Size;
  unsigned char Challenge1[MSR_CHALLENGE_SIZE];
  unsigned char SessionId[MSR_SESSION_ID_SIZE];
} MSR_AUTHENTICATE_DEVICE, *PMSR_AUTHENTICATE_DEVICE;
```

## Members


`Size`

If the optional <b>SessionId</b> is present, this will include the size of <b>SessionId[MSR_SESSION_ID_SIZE]</b>

`Challenge1`

The challenge token.

`SessionId`

The session ID. This is primarily used to identify each transaction so that you can prevent errors such as processing the same transaction twice.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicedriverinterface.h (include PointOfServiceDriverInterface.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn772101">IOCTL_POINT_OF_SERVICE_MSR_AUTHENTICATE_DEVICE</a>