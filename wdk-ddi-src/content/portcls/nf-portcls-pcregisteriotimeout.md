---
UID: NF.portcls.PcRegisterIoTimeout
title: PcRegisterIoTimeout function
author: windows-driver-content
description: The PcRegisterIoTimeout function registers a driver-supplied I/O-timer callback routine for a specified device object.
old-location: audio\pcregisteriotimeout.htm
old-project: audio
ms.assetid: 9cd7c366-1745-45b0-b9e9-87a259110621
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcRegisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PcRegisterIoTimeout
req.alt-loc: Portcls.lib,Portcls.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# PcRegisterIoTimeout function



## -description
The <b>PcRegisterIoTimeout</b> function registers a driver-supplied I/O-timer callback routine for a specified device object.

Once registered, the port-class driver calls the timer callback approximately once per second for as long as the device remains active.



## -syntax

````
NTSTATUS PcRegisterIoTimeout(
  _In_ PDEVICE_OBJECT    pDeviceObject,
  _In_ PIO_TIMER_ROUTINE pTimerRoutine,
  _In_ PVOID             pContext
);
````


## -parameters

### -param pDeviceObject [in]

Pointer to a device object representing a device on which I/O operations can time out. This parameter must point to a system structure of type <a href="kernel.device_object">DEVICE_OBJECT</a>. When calling the I/O-timer callback routine, the port class driver passes this pointer as the first of two call parameters. For more information, see the following Remarks section.


### -param pTimerRoutine [in]

Pointer to the driver-supplied I/O-timer callback routine. For more information, see the following Remarks section.


### -param pContext [in]

Pointer to the driver-specific context. When calling the I/O-timer callback routine, the port class driver passes this pointer as the second of two call parameters. For more information, see the following Remarks section.


## -returns
<b>PcRegisterIoTimeout</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. The following table shows some of the possible error codes.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Possibly indicates that a memory allocation failed inside the port-class driver.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>Possibly indicates that a timer callback with the same combination of device object, I/O-timer callback routine, and context is already registered.

 


## -remarks
An adapter driver calls the <b>PcRegisterIoTimeout</b> function to enable a low-resolution watchdog timer. Drivers use this function primarily to monitor devices that have no means to generate an event themselves if they fail to complete a previously initiated I/O operation within some maximum time interval.

After the driver calls <b>PcRegisterIoTimeout</b>, the port-class driver calls the driver's I/O-timer callback routine approximately once per second for as long as the device remains active. (The device is activated by an IRP_MN_START_DEVICE request and deactivated by an IRP_MN_STOP_DEVICE request.)

The driver can disable the timer by calling <a href="audio.pcunregisteriotimeout">PcUnregisterIoTimeout</a>.

Only one timer callback with a particular combination of device object, I/O-timer callback routine, and context can be registered at a time.

The meaning of the <i>pContext</i> parameter is determined by the adapter driver, but the driver typically sets this parameter to point to an object such as the miniport, miniport-stream, or adapter object.

The <i>pTimerRoutine </i>parameter is of type PIO_TIMER_ROUTINE, which is defined in ntddk.h to be

The <i>DeviceObject</i> and <i>Context</i> parameters are the same values that the adapter driver previously passed as call parameters to <b>PcRegisterIoTimeout</b>. The port-class driver calls the timer routine at IRQL DISPATCH_LEVEL. The timer routine must not contain pageable code.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
The PortCls system driver implements the PcRegisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Portcls.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.pcunregisteriotimeout">PcUnregisterIoTimeout</a>
</dt>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterIoTimeout function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

