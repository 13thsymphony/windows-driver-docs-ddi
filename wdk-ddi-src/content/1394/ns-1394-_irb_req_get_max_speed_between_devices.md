---
UID: NS:1394._IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES
title: "_IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES"
author: windows-driver-content
description: This structure contains the fields necessary in order for the Bus driver to carry out a GetMaxSpeedBetweenDevices request.
old-location: ieee\irb_req_get_max_speed_between_devices.htm
old-project: IEEE
ms.assetid: 7B296D94-32DB-4190-935F-F1CC5F566706
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IEEE.irb_req_get_max_speed_between_devices, 1394/IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES, IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES, _IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES, IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES
product: Windows
targetos: Windows
req.typenames: IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES
---

# _IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES structure
This structure contains the fields necessary in order for the Bus driver to carry out a
<b>GetMaxSpeedBetweenDevices</b> request.

## Syntax
````
typedef struct _IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES {
  ULONG          fulFlags;
  ULONG          ulNumberOfDestinations;
  PDEVICE_OBJECT hDestinationDeviceObjects[64];
  ULONG          fulSpeed;
} IRB_REQ_GET_MAX_SPEED_BETWEEN_DEVICES;
````

## Members


`fulFlags`

Specifies the source device. Zero indicates the calling device. USE_LOCAL_NODE indicates the computer itself.

<div class="alert"><b>Note</b>  In Windows 7, the new 1394 bus driver returns only the speed between the local node and the device. The USE_LOCAL_NODE flag must be set in the <b>u.GetMaxSpeedBetweenDevices.fulFlags</b> parameter.</div>
<div> </div>

`fulSpeed`

Specifies the maximum speed returned.

`hDestinationDeviceObjects`

Points to an array of the device objects of the destination devices.

`ulNumberOfDestinations`

Specifies the number of destination devices.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | 1394.h |