---
UID: NF:wdfdevice.WdfDeviceGetSystemPowerAction
title: WdfDeviceGetSystemPowerAction function
author: windows-driver-content
description: The WdfDeviceGetSystemPowerAction method returns the system power action, if any, that is currently occurring for the computer.
old-location: wdf\wdfdevicegetsystempoweraction.htm
old-project: wdf
ms.assetid: 5c4e44cd-94a3-4265-b195-7a5711d8035d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceGetSystemPowerAction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 2.0
req.alt-api: WdfDeviceGetSystemPowerAction
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceGetSystemPowerAction function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetSystemPowerAction</b> method returns the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a>, if any, that is currently occurring for the computer. 



## -syntax

````
POWER_ACTION WdfDeviceGetSystemPowerAction(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -returns
<b>WdfDeviceGetSystemPowerAction</b> returns a POWER_ACTION-typed enumerator value. The value indicates the <a href="https://msdn.microsoft.com/e8ab99d4-c18d-4ba8-bfe8-8eebb881c384">system power action</a> that is currently occurring for the computer. For more information, see the following Remarks section. The POWER_ACTION enumeration is defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
The <b>WdfDeviceGetSystemPowerAction</b> method enables a driver to determine whether a device's power transition is occurring because the device is idle (or waking up), or because the entire computer is entering (or leaving) a low-power state. 

The driver must call <b>WdfDeviceGetSystemPowerAction</b> only from the event callback functions that the framework calls when the device is <a href="wdf.a_device_enters_a_low_power_state">entering a low-power state</a> or <a href="wdf.a_device_returns_to_its_working_state">returning to its working state</a>. 

The value that <b>WdfDeviceGetSystemPowerAction</b> returns depends on the following situations:

If the computer is entering a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer is entering the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is entering its S1, S2, or S3 low-power state.

If the computer is returning to its working (S0) state from a low-power state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns the reason that the computer entered the low-power state. For example, the method returns <b>PowerActionSleep</b> if the computer is leaving its S1, S2, or S3 low-power state.

If the computer is powering up (after having been turned off) when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

If the device is entering a low-power idle state or returning to its working (D0) state when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, while the rest of the system remains at its working (S0) state, the method returns <b>PowerActionNone</b>.

If the computer and the device are both in their working states when the driver calls <b>WdfDeviceGetSystemPowerAction</b>, the method returns <b>PowerActionNone</b>.

For more information about low-power states, see <a href="https://msdn.microsoft.com/07d7c460-4316-40a9-b502-f7c1bd1182c2">A Device Enters a Low-Power State</a>.

The following code example obtains the power transition activity that is currently occurring for the computer.</p>