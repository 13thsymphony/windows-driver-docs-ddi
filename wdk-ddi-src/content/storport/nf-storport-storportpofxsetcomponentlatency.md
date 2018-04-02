---
UID: NF:storport.StorPortPoFxSetComponentLatency
title: StorPortPoFxSetComponentLatency function
author: windows-driver-content
description: The StorPortPoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified storage device component.
old-location: storage\storportpofxsetcomponentlatency.htm
old-project: storage
ms.assetid: F175ED42-3DB6-4568-96CA-EFC283B14887
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortPoFxSetComponentLatency, StorPortPoFxSetComponentLatency routine [Storage Devices], storage.storportpofxsetcomponentlatency, storport/StorPortPoFxSetComponentLatency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortPoFxSetComponentLatency
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortPoFxSetComponentLatency function
The <b>StorPortPoFxSetComponentLatency</b> routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified storage device component.

## Syntax

```
ULONG StorPortPoFxSetComponentLatency(
  PVOID         HwDeviceExtension,
  PSTOR_ADDRESS Address,
  ULONG         Component,
  ULONGLONG     Latency
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA). This is the device extension used to register the device in a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh920421">StorPortInitializePoFxPower</a>.

`Address`

The address of a storage device unit. This parameter is <b>NULL</b> when setting the latency of a storage adapter component.

`Component`

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh920429">STOR_POFX_DEVICE</a> structure that the miniport driver registered for the device with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh920421">StorPortInitializePoFxPower</a>. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

`Latency`

The time, in units of 100 nanoseconds, that the storage device component can tolerate  for a transition from an  idle state the active state.


## Return Value

The <b>StorPortPoFxSetComponentLatency</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The component latency successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>Device</i> is NULL.

-or-

<i>Address</i> points to an invalid unit address structure.

-or-

The storage device specified by <i>Address</i> is not found.

-or-

The index in <i>Component</i> specifies a component greater than the component count for the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The storage device is  not registered with the  power management framework (PoFx).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | storport.h |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439531">PoFxSetComponentLatency</a>