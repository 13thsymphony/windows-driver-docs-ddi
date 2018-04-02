---
UID: NE:ks.KSEVENT_DEVICE
title: KSEVENT_DEVICE
author: windows-driver-content
description: Specifies event notifications that the driver generates to indicate that a device has been lost or preempted.
old-location: stream\ksevent_device.htm
old-project: stream
ms.assetid: 92594bdd-a458-4262-ac4c-013cffb7a725
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KSEVENT_DEVICE, KSEVENT_DEVICE enumeration [Streaming Media Devices], KSEVENT_DEVICE_LOST, KSEVENT_DEVICE_PREEMPTED, ks/KSEVENT_DEVICE, ks/KSEVENT_DEVICE_LOST, ks/KSEVENT_DEVICE_PREEMPTED, stream.ksevent_device
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Ks.h
api_name:
-	KSEVENT_DEVICE
product: Windows
targetos: Windows
req.typenames: KSEVENT_DEVICE
---

# KSEVENT_DEVICE Enumeration
Specifies event notifications that the driver generates to indicate that a device has been lost or preempted.

## Syntax
```
typedef enum KSEVENT_DEVICE {
  KSEVENT_DEVICE_LOST          ,
  KSEVENT_DEVICE_PREEMPTED     ,
  KSEVENT_DEVICE_THERMAL_HIGH  ,
  KSEVENT_DEVICE_THERMAL_LOW
} ;
```

## Constants

<table>
            
                <tr>
                    <td>KSEVENT_DEVICE_LOST</td>
                    <td>A camera device has been removed from the system. See <a href="https://msdn.microsoft.com/library/windows/hardware/jj156039">KSEVENT_DEVICE_LOST</a>.</td>
                </tr>
            
                <tr>
                    <td>KSEVENT_DEVICE_PREEMPTED</td>
                    <td>A camera device has been preempted by a new Windows app. See <a href="https://msdn.microsoft.com/library/windows/hardware/jj156040">KSEVENT_DEVICE_PREEMPTED</a>.</td>
                </tr>
            
                <tr>
                    <td>KSEVENT_DEVICE_THERMAL_HIGH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>KSEVENT_DEVICE_THERMAL_LOW</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj156039">KSEVENT_DEVICE_LOST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj156040">KSEVENT_DEVICE_PREEMPTED</a>