---
UID: NF.ursdevice.UrsReportHardwareEvent
title: UrsReportHardwareEvent
author: windows-driver-content
description: Notifies the USB dual-role class extension about a new hardware event.
old-location: buses\ursreporthardwareevent.htm
ms.assetid: 2BC80D99-5265-4D0C-A447-5CC2112F53F8
ms.author: windowsdriverdev
ms.date: 11/3/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: usbref
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UrsReportHardwareEvent
req.alt-loc: Urscxstub.lib,Urscxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: HIGH_LEVEL
ms.keywords: UrsReportHardwareEvent
req.iface: 
req.product: Windows 10 or later.
---

# UrsReportHardwareEvent function



## -description
<p>Notifies the USB dual-role class extension about a new hardware event.</p>


## -syntax

````
FORCEINLINE NTSTATUS UrsReportHardwareEvent(
  _In_ WDFDEVICE          Device,
  _In_ URS_HARDWARE_EVENT HardwareEvent
);
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>A handle to the framework device object that the client driver retrieved in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.</p>
</dd>

### -param <i>HardwareEvent</i> [in]

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628022">URS_HARDWARE_EVENT</a>-type value that indicates the type of event that occurred.</p>
</dd>
</dl>

## -returns
<p>The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. </p>

## -remarks
<p>Before reporting any hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628018">UrsSetHardwareEventSupport</a>.</p>

<p>The client driver cannot pass <b>UrsHardwareEventNone</b> as the <i>HardwareEvent</i> parameter value. That value is reserved for internal use.</p>

<p>The client driver must call this method to report any hardware event, such as ID-pin interrupts. Typically, in the driver's implementation of the <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback, the driver reads the  ID-pin state and reports the event to the class extension by calling this method. </p>

<p>Before reporting any hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628018">UrsSetHardwareEventSupport</a>.</p>

<p>The client driver cannot pass <b>UrsHardwareEventNone</b> as the <i>HardwareEvent</i> parameter value. That value is reserved for internal use.</p>

<p>The client driver must call this method to report any hardware event, such as ID-pin interrupts. Typically, in the driver's implementation of the <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback, the driver reads the  ID-pin state and reports the event to the class extension by calling this method. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ursdevice.h (include Urscx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Urscxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>HIGH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt628018">UrsSetHardwareEventSupport</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UrsReportHardwareEvent function%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
