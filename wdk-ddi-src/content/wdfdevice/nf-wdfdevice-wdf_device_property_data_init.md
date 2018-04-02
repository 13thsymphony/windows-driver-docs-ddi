---
UID: NF:wdfdevice.WDF_DEVICE_PROPERTY_DATA_INIT
title: WDF_DEVICE_PROPERTY_DATA_INIT function
author: windows-driver-content
description: The WDF_DEVICE_PROPERTY_DATA_INIT function initializes a driver's WDF_DEVICE_PROPERTY_DATA structure.
old-location: wdf\wdf_device_property_data_init.htm
old-project: wdf
ms.assetid: D3A7646A-49A8-499E-A63A-BCD222DF7804
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_DEVICE_PROPERTY_DATA_INIT, WDF_DEVICE_PROPERTY_DATA_INIT function, wdf.wdf_device_property_data_init, wdfdevice/WDF_DEVICE_PROPERTY_DATA_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
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
-	wdfdevice.h
api_name:
-	WDF_DEVICE_PROPERTY_DATA_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WDF_DEVICE_PROPERTY_DATA_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265632">WDF_DEVICE_PROPERTY_DATA</a> structure.

## Syntax

```
void WDF_DEVICE_PROPERTY_DATA_INIT(
  PWDF_DEVICE_PROPERTY_DATA PropertyData,
  const DEVPROPKEY          *PropertyKey
);
```

## Parameters

`PropertyData`

A pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/dn265632">WDF_DEVICE_PROPERTY_DATA</a> structure.

`PropertyKey`

A pointer to a <b>DEVPROPKEY</b> structure that specifies the device property key.


## Return Value

This function does not return a value.

## Remarks

Before calling the following methods, a driver must call <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265632">WDF_DEVICE_PROPERTY_DATA</a> structure.

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265599">WdfDeviceAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265601">WdfDeviceAssignProperty</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265608">WdfDeviceQueryPropertyEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265612">WdfFdoInitAllocAndQueryPropertyEx</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265613">WdfFdoInitQueryPropertyEx</a>
</li>
</ul>
The <b>WDF_DEVICE_PROPERTY_DATA_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/dn265632">WDF_DEVICE_PROPERTY_DATA</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>PropertyKey</b> member to the specified value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265632">WDF_DEVICE_PROPERTY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265599">WdfDeviceAllocAndQueryPropertyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265601">WdfDeviceAssignProperty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265608">WdfDeviceQueryPropertyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265612">WdfFdoInitAllocAndQueryPropertyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265613">WdfFdoInitQueryPropertyEx</a>