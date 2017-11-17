---
UID: NS.wdm._IO_SESSION_STATE_NOTIFICATION
title: IO_SESSION_STATE_NOTIFICATION
author: windows-driver-content
description: The IO_SESSION_STATE_NOTIFICATION structure contains information that a kernel-mode driver supplies to the IoRegisterContainerNotification routine when the driver registers to receive notifications of session events.
old-location: kernel\io_session_state_notification.htm
ms.assetid: 19ff9c3a-d416-4468-b5a5-e2e6e896802a
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_SESSION_STATE_NOTIFICATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
ms.keywords: IO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_NOTIFICATION, *PIO_SESSION_STATE_NOTIFICATION
req.iface: 
req.product: Windows 10 or later.
---

# IO_SESSION_STATE_NOTIFICATION structure



## -description
<p>The <b>IO_SESSION_STATE_NOTIFICATION</b> structure contains information that a kernel-mode driver supplies to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549501">IoRegisterContainerNotification</a> routine when the driver registers to receive notifications of session events.</p>


## -syntax

````
typedef struct _IO_SESSION_STATE_NOTIFICATION {
  ULONG Size;
  ULONG Flags;
  PVOID IoObject;
  ULONG EventMask;
  PVOID Context;
} IO_SESSION_STATE_NOTIFICATION, *PIO_SESSION_STATE_NOTIFICATION;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The size, in bytes, of the <b>IO_SESSION_STATE_NOTIFICATION</b> structure.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>No flags are currently defined for this member. Set to zero. </p>
</dd>

### -field <b>IoObject</b>

<dd>
<p>A pointer to an I/O object owned by the driver. This member can point to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure. The I/O object must remain valid for the lifetime of the registration. Before you delete a registered device object, unload a registered driver, or close a registered file object, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550396">IoUnregisterContainerNotification</a> routine to cancel the registration. A driver can maintain simultaneous registrations for more than one I/O object, but it cannot create more than one active registration for the same I/O object. </p>
</dd>

### -field <b>EventMask</b>

<dd>
<p>Mask bits for session events. These mask bits indicate the events for which the driver requests notifications.</p>
<p>To register to receive notifications of session events, a kernel-mode driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549501">IoRegisterContainerNotification</a> routine. To specify the session events for which the driver wants to receive notifications, the driver sets this structure's <b>EventMask</b> member to the bitwise OR of one or more <b>IO_SESSION_STATE_<i>XXX</i></b> constants. </p>
<p>Set this member to the bitwise OR of one or more of the following <b>IO_SESSION_STATE_<i>XXX</i></b> constants:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_ALL_EVENTS"></a><a id="io_session_state_all_events"></a><dl>

### -field <b>IO_SESSION_STATE_ALL_EVENTS</b>


### -field 0xffffffff

</dl>
</td>
<td width="60%">
<p>Send notifications of all session events.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_CREATION_EVENT"></a><a id="io_session_state_creation_event"></a><dl>

### -field <b>IO_SESSION_STATE_CREATION_EVENT</b>


### -field 0x00000001

</dl>
</td>
<td width="60%">
<p>Send a notification when the user session is created.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_TERMINATION_EVENT"></a><a id="io_session_state_termination_event"></a><dl>

### -field <b>IO_SESSION_STATE_TERMINATION_EVENT</b>


### -field 0x00000002

</dl>
</td>
<td width="60%">
<p>Send a notification when the user session ends.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_CONNECT_EVENT"></a><a id="io_session_state_connect_event"></a><dl>

### -field <b>IO_SESSION_STATE_CONNECT_EVENT</b>


### -field 0x00000004

</dl>
</td>
<td width="60%">
<p>Send a notification when the user session is connected.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_DISCONNECT_EVENT"></a><a id="io_session_state_disconnect_event"></a><dl>

### -field <b>IO_SESSION_STATE_DISCONNECT_EVENT</b>


### -field 0x00000008

</dl>
</td>
<td width="60%">
<p>Send a notification when the user session is disconnected.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_LOGON_EVENT"></a><a id="io_session_state_logon_event"></a><dl>

### -field <b>IO_SESSION_STATE_LOGON_EVENT</b>


### -field 0x00000010

</dl>
</td>
<td width="60%">
<p>Send a notification when the user logs on to the session.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_LOGOFF_EVENT"></a><a id="io_session_state_logoff_event"></a><dl>

### -field <b>IO_SESSION_STATE_LOGOFF_EVENT</b>


### -field 0x00000020

</dl>
</td>
<td width="60%">
<p>Send a notification when the user logs off of the session.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_VALID_EVENT_MASK"></a><a id="io_session_state_valid_event_mask"></a><dl>

### -field <b>IO_SESSION_STATE_VALID_EVENT_MASK</b>


### -field 0x0000003f

</dl>
</td>
<td width="60%">
<p>Send a notification when any type of session event occurs.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>Context</b>

<dd>
<p>A pointer to a context buffer in which the driver can store its private data for a particular session notification registration. The I/O manager passes this pointer to the driver's notification callback routine (specified by the <b>IoRegisterContainerNotification</b> routine's <i>CallbackFunction</i> parameter). The I/O manager does not try to validate the <i>Context</i> pointer or to access the buffer that it points to. This member can be <b>NULL</b> if the driver does not require a context buffer. </p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <b>IoRegisterContainerNotification</b> routine. A driver that calls <b>IoRegisterContainerNotification</b> uses this structure to specify the session event notifications that it is registering for.</p>

<p>A per-session device object represents a device that can be accessed only by a particular user session. If a driver sets the <b>IoObject</b> member to point to a device object that is a per-session device object, <b>IoRegisterContainerNotification</b> registers the driver to receive only notifications of events that occur in the session that is represented by the device object. If <b>IoObject</b> points to a device object that is not a per-session device object, or if <b>IoObject</b> points to an object that is not a device object, <b>IoRegisterContainerNotification</b> registers the driver to receive notifications of events that occur in all sessions on the computer.</p>

<p>To determine whether a device object is a per-session device object, a driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549206">IoGetDevicePropertyData</a> routine to query the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542651">DEVPKEY_Device_SessionId</a> property key in the property store of the device object. If the <b>DEVPKEY_Device_SessionId</b> property exists and the value of the property is set to a nonzero <a href="http://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier, the device object is a per-session device object. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542651">DEVPKEY_Device_SessionId</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows 7 and later versions of the Windows operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542651">DEVPKEY_Device_SessionId</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549206">IoGetDevicePropertyData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549501">IoRegisterContainerNotification</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_SESSION_STATE_NOTIFICATION structure%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
