---
UID : NC:ufxclient.EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
title : EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
author : windows-driver-content
description : The client driver's implementation to set or clear the specified power feature on the function controller.
old-location : buses\evt_ufx_device_super_speed_power_feature.htm
old-project : usbref
ms.assetid : 5A2B787B-13B8-48E9-B53E-7F6409820B88
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.evt_ufx_device_super_speed_power_feature, EvtUfxDeviceSuperSpeedPowerFeature callback function [Buses], EvtUfxDeviceSuperSpeedPowerFeature, EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE, EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE, ufxclient/EvtUfxDeviceSuperSpeedPowerFeature, PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback function pointer [Buses], PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product : Windows 10 or later.
---


# EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE function
The client driver's implementation to set or clear the specified power feature on the function controller.

## Syntax

```
EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE EvtUfxDeviceSuperSpeedPowerFeature;

void EvtUfxDeviceSuperSpeedPowerFeature(
  UFXDEVICE ,
  USHORT ,
  BOOLEAN 
)
{...}
```

## Parameters

``



``



``




## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</i> implementation with the USB function class extension (UFX) by calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> method.

This event callback is only required for controllers that support SuperSpeed operation.

The client driver indicates completion of this event by calling the <a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxclient.h |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>

<a href="..\ufxclient\nf-ufxclient-ufxdeviceeventcomplete.md">UfxDeviceEventComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>