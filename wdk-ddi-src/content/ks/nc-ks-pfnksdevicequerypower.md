---
UID: NC.ks.PFNKSDEVICEQUERYPOWER
title: PFNKSDEVICEQUERYPOWER
author: windows-driver-content
description: AVStream calls a minidriver's AVStrMiniDeviceQueryPower routine when it receives an IRP_MN_QUERY_POWER request.
old-location: stream\avstrminidevicequerypower.htm
old-project: stream
ms.assetid: db839cde-cb3e-47f2-9a06-54e37ac7ac67
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVStrMiniDeviceQueryPower
req.alt-loc: ks.h
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
req.iface: 
---

# PFNKSDEVICEQUERYPOWER callback



## -description
<p>AVStream calls a minidriver's <i>AVStrMiniDeviceQueryPower</i> routine when it receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> request.</p>


## -prototype

````
PFNKSDEVICEQUERYPOWER AVStrMiniDeviceQueryPower;

NTSTATUS AVStrMiniDeviceQueryPower(
  _In_ PKSDEVICE          Device,
  _In_ PIRP               Irp,
  _In_ DEVICE_POWER_STATE DeviceTo,
  _In_ DEVICE_POWER_STATE DeviceFrom,
  _In_ SYSTEM_POWER_STATE SystemTo,
  _In_ SYSTEM_POWER_STATE SystemFrom,
  _In_ POWER_ACTION       Action
)
{ ... }
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure that dispatched the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>.</p>
</dd>

### -param <i>Irp</i> [in]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> issued by <i>Device</i>.</p>
</dd>

### -param <i>DeviceTo</i> [in]

<dd>
<p>The power state requested by the issuer of <i>Irp</i>.</p>
</dd>

### -param <i>DeviceFrom</i> [in]

<dd>
<p>The current device power state.</p>
</dd>

### -param <i>SystemTo</i> [in]

<dd>
<p>System state to transition to, specified when a system power state transition is being queried. This value is unspecified if the call is due to a device power state change query.</p>
</dd>

### -param <i>SystemFrom</i> [in]

<dd>
<p>Current system state, specified when a system power state transition is being queried. This value is unspecified if the call is due to a device power state change query.</p>
</dd>

### -param <i>Action</i> [in]

<dd>
<p>Specifies additional information about the requested transition. Possible values are enumerators of the POWER_ACTION type.</p>
</dd>
</dl>

## -returns
<p>Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. By returning STATUS_SUCCESS, the driver guarantees that it will not start any operation that would change its ability to set the requested power state. The driver should queue any IRP that would require such an operation until it completes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> that returns the device to an acceptable power state.</p>

## -remarks
<p>The power manager or a device power policy owner sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> request to determine whether it can change the system or device power state (for example, to go to sleep).</p>

<p>If a driver fails an IRP_MN_QUERY_POWER request for a system power state, the power manager typically responds by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>. Usually, this IRP will reaffirm the current system state. However, it is possible that drivers might receive an IRP_MN_SET_POWER to the queried state or to some other intermediate state. Drivers should be prepared to handle these situations.</p>

<p>The minidriver specifies this routine's address in the <b>QueryPower</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.</p>

<p>This routine is optional.</p>

<p>The power manager or a device power policy owner sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a> request to determine whether it can change the system or device power state (for example, to go to sleep).</p>

<p>If a driver fails an IRP_MN_QUERY_POWER request for a system power state, the power manager typically responds by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>. Usually, this IRP will reaffirm the current system state. However, it is possible that drivers might receive an IRP_MN_SET_POWER to the queried state or to some other intermediate state. Drivers should be prepared to handle these situations.</p>

<p>The minidriver specifies this routine's address in the <b>QueryPower</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.</p>

<p>This routine is optional.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551699">IRP_MN_QUERY_POWER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVStrMiniDeviceQueryPower routine%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
