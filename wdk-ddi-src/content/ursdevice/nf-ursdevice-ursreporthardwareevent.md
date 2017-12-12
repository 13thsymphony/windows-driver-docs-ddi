---
UID: NF.ursdevice.UrsReportHardwareEvent
title: UrsReportHardwareEvent function
author: windows-driver-content
description: Notifies the USB dual-role class extension about a new hardware event.
old-location: buses\ursreporthardwareevent.htm
old-project: usbref
ms.assetid: 2BC80D99-5265-4D0C-A447-5CC2112F53F8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UrsReportHardwareEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.product: Windows 10 or later.
---

# UrsReportHardwareEvent function



## -description
Notifies the USB dual-role class extension about a new hardware event.



## -syntax

````
FORCEINLINE NTSTATUS UrsReportHardwareEvent(
  _In_ WDFDEVICE          Device,
  _In_ URS_HARDWARE_EVENT HardwareEvent
);
````


## -parameters

### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>.


### -param HardwareEvent [in]

A <a href="buses.urs_hardware_event">URS_HARDWARE_EVENT</a>-type value that indicates the type of event that occurred.


## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 


## -remarks
Before reporting any hardware events, the client driver for the dual-role controller must indicate to the class extension that the driver supports hardware events by calling <a href="buses.urssethardwareeventsupport">UrsSetHardwareEventSupport</a>.

The client driver cannot pass <b>UrsHardwareEventNone</b> as the <i>HardwareEvent</i> parameter value. That value is reserved for internal use.

The client driver must call this method to report any hardware event, such as ID-pin interrupts. Typically, in the driver's implementation of the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback, the driver reads the  ID-pin state and reports the event to the class extension by calling this method. 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ursdevice.h (include Urscx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Urscxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
HIGH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.urssethardwareeventsupport">UrsSetHardwareEventSupport</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UrsReportHardwareEvent function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

