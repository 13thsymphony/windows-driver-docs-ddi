---
UID: NF:wdm.IoUnregisterPlugPlayNotificationEx
title: IoUnregisterPlugPlayNotificationEx function
author: windows-driver-content
description: The IoUnregisterPlugPlayNotificationEx routine cancels the registration of a driver's callback routine for notifications of Plug and Play (PnP) events.
old-location: kernel\iounregisterplugplaynotificationex.htm
old-project: kernel
ms.assetid: 72545150-5fd8-4770-aab2-b49d80c1e865
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoUnregisterPlugPlayNotificationEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoUnregisterPlugPlayNotificationEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoUnregisterPlugPlayNotificationEx function



## -description
The <b>IoUnregisterPlugPlayNotificationEx</b> routine cancels the registration of a driver's callback routine for notifications of Plug and Play (PnP) events. 



## -syntax

````
NTSTATUS IoUnregisterPlugPlayNotificationEx(
  _In_ PVOID NotificationEntry
);
````


## -parameters

### -param NotificationEntry [in]

A pointer to an opaque value that represents the registration to cancel. The caller previously obtained this value by calling the <a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a> routine. 


## -returns
<b>IoUnregisterPlugPlayNotificationEx</b> returns STATUS_SUCCESS if the <i>NotificationEntry</i> parameter is valid. 


## -remarks
A kernel-mode driver calls this routine to remove a registration to receive PnP notifications. That is, an <b>IoUnregisterPlugPlayNotificationEx</b> call cancels the registration of a driver callback routine for one PnP event category. The driver previously obtained this registration by calling the <b>IoRegisterPlugPlayNotification</b> routine.

After an <b>IoUnregisterPlugPlayNotificationEx</b> call returns, the specified registration is canceled and no further callbacks can occur.

The <a href="..\wdm\nf-wdm-iounregisterplugplaynotification.md">IoUnregisterPlugPlayNotification</a> routine is similar to <b>IoUnregisterPlugPlayNotificationEx</b>, except that it cannot guarantee that no further callbacks can occur after a <b>IoUnregisterPlugPlayNotification</b> call returns.

Frequently, a driver calls <b>IoUnregisterPlugPlayNotificationEx</b> from a notification callback routine. In most cases, the driver can safely delete the registration of the notification callback routine in this way. However, it is unsafe for a notification callback routine to call <b>IoUnregisterPlugPlayNotificationEx</b> to unregister itself if the following are both true:

The callback routine must not call any routine that might block the execution of the thread on which the callback routine is running. For example, if a poorly designed callback routine places a work item that calls <b>IoUnregisterPlugPlayNotificationEx</b> in the work item queue, and then waits for a worker thread to complete the work item, it would result in a deadlock of the operating system.

Drivers should cancel the registration of a notification callback routine first, and then free any context buffer that is associated with the routine.

A driver cannot be unloaded until it removes all of its PnP notification registrations because each active registration holds a counted reference to the <a href="https://msdn.microsoft.com/497ee2dc-671d-408e-b228-16dc24532375">driver object</a> that represents the loaded image of the driver.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565480">Using PnP Notification</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iounregisterplugplaynotification.md">IoUnregisterPlugPlayNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUnregisterPlugPlayNotificationEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

