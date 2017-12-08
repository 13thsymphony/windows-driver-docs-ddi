---
UID: NF.ndis.NdisMIdleNotificationComplete
title: NdisMIdleNotificationComplete function
author: windows-driver-content
description: Miniport drivers call NdisMIdleNotificationComplete to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's MiniportIdleNotification handler function.
old-location: netvista\ndismidlenotificationcomplete.htm
old-project: netvista
ms.assetid: A6936B25-F804-4EF3-909C-7838346AC37E
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisMIdleNotificationComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMIdleNotificationComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMIdleNotificationComplete function



## -description

Miniport drivers call <b>NdisMIdleNotificationComplete</b> to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's  <a href="..\ndis\nc-ndis-miniport_idle_notification.md">MiniportIdleNotification</a> handler function.

Miniport drivers call <b>NdisMIdleNotificationComplete</b> to complete a pending idle notification for an NDIS selective suspend operation. NDIS begins the operation when it calls the driver's  <a href="..\ndis\nc-ndis-miniport_idle_notification.md">MiniportIdleNotification</a> handler function.


## -syntax

````
VOID NdisMIdleNotificationComplete(
  _In_ NDIS_HANDLE  MiniportAdapterHandle
);
````


## -parameters

### -param  MiniportAdapterHandle [in]

The network adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.



## -returns
None

## -remarks
NDIS calls the miniport driver's <a href="..\ndis\nc-ndis-miniport_cancel_idle_notification.md">MiniportCancelIdleNotification</a> handler function to complete a pending idle notification for an NDIS selective suspend operation. Miniport drivers  call <b>NdisMIdleNotificationComplete</b> to notify NDIS that the idle notification is complete for the network adapter. NDIS then transitions the adapter to a full-power state in order to complete the selective suspend operation.

Before the miniport drivers calls <b>NdisMIdleNotificationComplete</b>, it must cancel any bus-specific  I/O request packets (IRPs) that it may have previously issued for the idle notification.  

For example, when NDIS calls the <a href="..\ndis\nc-ndis-miniport_idle_notification.md">MiniportIdleNotification</a> function, the USB miniport driver issues the bus-specific USB idle request IRP (<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_submit_idle_notification.md">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>) to the USB bus driver. When NDIS calls the driver's <a href="..\ndis\nc-ndis-miniport_cancel_idle_notification.md">MiniportCancelIdleNotification</a> function, the driver cancels the IRP. When the USB bus driver calls the completion routine that is associated with the IRP, it confirms that the IRP is cancelled and the device can resume to a full-power state. In the context of the completion routine, the miniport driver calls <b>NdisMIdleNotificationComplete</b>.  For more information, see <a href="netvista.implementing_a_usb_idle_request_irp_completion_routine">Implementing a USB Idle Request IRP Completion Routine</a>.

For more information on how miniport drivers complete NDIS selective suspend  idle notifications, see <a href="netvista.completing_the_ndis_selective_suspend_idle_notification">Completing the NDIS Selective Suspend Idle Notification</a>.

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
Supported in NDIS 6.30 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_submit_idle_notification.md">IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_cancel_idle_notification.md">MiniportCancelIdleNotification</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_idle_notification.md">MiniportIdleNotification</a>
</dt>
<dt>
<a href="netvista.ndismidlenotificationconfirm">NdisMIdleNotificationConfirm</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMIdleNotificationComplete function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
