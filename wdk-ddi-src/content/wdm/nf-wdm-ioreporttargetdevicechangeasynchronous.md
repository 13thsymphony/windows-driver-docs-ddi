---
UID: NF.wdm.IoReportTargetDeviceChangeAsynchronous
title: IoReportTargetDeviceChangeAsynchronous function
author: windows-driver-content
description: The IoReportTargetDeviceChangeAsynchronous routine notifies the PnP manager that a custom event has occurred on a device.
old-location: kernel\ioreporttargetdevicechangeasynchronous.htm
old-project: kernel
ms.assetid: 69ffe74f-59f9-41d6-a494-ee00be5bec62
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IoReportTargetDeviceChangeAsynchronous
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoReportTargetDeviceChangeAsynchronous
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# IoReportTargetDeviceChangeAsynchronous function



## -description
The <b>IoReportTargetDeviceChangeAsynchronous</b> routine notifies the PnP manager that a custom event has occurred on a device. 



## -syntax

````
NTSTATUS IoReportTargetDeviceChangeAsynchronous(
  _In_     PDEVICE_OBJECT                   PhysicalDeviceObject,
  _In_     PVOID                            NotificationStructure,
  _In_opt_ PDEVICE_CHANGE_COMPLETE_CALLBACK Callback,
  _Inout_  PVOID                            Context
);
````


## -parameters

### -param PhysicalDeviceObject [in]

Pointer to the PDO of the device being reported. 


### -param NotificationStructure [in]

Pointer to a caller-supplied <a href="kernel.target_device_custom_notification">TARGET_DEVICE_CUSTOM_NOTIFICATION</a> structure describing the custom event. The PnP manager sends this structure to drivers that registered for notification of the event.

<i>NotificationStructure</i>.<b>FileObject</b> must be <b>NULL</b>. <i>NotificationStructure</i>.<b>Event</b> must contain the custom GUID for the event. The other fields of the <i>NotificationStructure</i> must be filled in as appropriate for the custom event.

The PnP manager fills in the <i>NotificationStructure</i>.<b>FileObject</b> field when it sends notifications to registrants.


### -param Callback [in, optional]

Optionally points to a caller-supplied routine that the PnP manager calls after it finishes notifying drivers that registered for this custom event.

The callback routine has the following type:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PDEVICE_CHANGE_COMPLETE_CALLBACK)(
    IN PVOID Context
    );</pre>
</td>
</tr>
</table></span></div>
A device-change-complete callback routine should not block and must not call synchronous routines that generate PnP events.

The PnP manager calls device-change-complete callback routines at IRQL = PASSIVE_LEVEL.


### -param Context [in, out]

Optionally points to a caller-supplied context structure that the PnP manager passes to the <i>Callback</i> routine. The caller must allocate this structure from nonpaged memory. 


## -returns
<b>IoReportTargetDeviceChangeAsynchronous</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status values include the following.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The caller specified a system PnP event, such as GUID_TARGET_DEVICE_QUERY_REMOVE. This routine is only for custom events.

 


## -remarks
After the <b>IoReportTargetDeviceChangeAsynchronous</b> routine notifies the PnP manager that a custom event has occurred on a device, the routine returns immediately; it does not wait while the PnP manager sends notification of the event to drivers that registered for notification on the device. Do not use this routine to report system PnP events, such as GUID_TARGET_DEVICE_REMOVE_COMPLETE.

A driver that defines a custom device event calls <b>IoReportTargetDeviceChangeAsynchronous</b> to inform the PnP manager that the custom event has occurred. Custom notification can be used for events like a volume label change.

The custom notification structure contains a driver-defined event with its own GUID. Driver writers can generate GUIDs with Uuidgen.exe or Guidgen.exe (which are included in the Microsoft Windows SDK).

When a driver calls this routine while handling an event, an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>, or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551760">IRP_MN_SURPRISE_REMOVAL</a>, the PnP manager calls the driver's <i>Callback</i> routine after the driver returns and the stack unwinds.

Callers of <b>IoReportTargetDeviceChangeAsynchronous</b> must be running at IRQL &lt;= DISPATCH_LEVEL. If a driver writer calls this routine at IRQL = DISPATCH_LEVEL, the <i>NotificationStructure</i> must be allocated from nonpaged memory.


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL (see Remarks section)

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ioreporttargetdevicechange">IoReportTargetDeviceChange</a>
</dt>
<dt>
<a href="kernel.target_device_custom_notification">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoReportTargetDeviceChangeAsynchronous routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

