---
UID: NC:storport.HW_TIMER
title: HW_TIMER
author: windows-driver-content
description: The HwStorTimer routine is called after the interval that is specified when the miniport driver called StorPortNotification with the RequestTimerCall NotificationType value.
old-location: storage\hwstortimer.htm
old-project: storage
ms.assetid: 61aced1b-9f8a-454a-901c-561ec6179873
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwStorTimer
req.alt-loc: Storport.h
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
req.typenames: *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_TIMER callback



## -description
The <b>HwStorTimer</b> routine is called after the interval that is specified when the miniport driver called <a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a> with the <b>RequestTimerCall</b><i> NotificationType</i> value.



## -prototype

````
HW_TIMER HwStorTimer;

VOID HwStorTimer(
   IN PVOID DeviceExtension
)
{ ... }
````


## -parameters

### -param DeviceExtension 

A pointer to the miniport driver's per HBA storage area.


## -returns
None


## -remarks
The name <b>HwStorTimer</b> is only a placeholder. The actual prototype of this routine is defined in <i>Srb.h</i> as follows:

If the miniport opts into multi-channel support, the StartIo spin lock is still taken. However, if the miniport has requested multiple channel support via PERF_CONFIGURATION_DATA, the StartIo spin lock is not taken or checked before the call to <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> in the miniport.  This means that the <i>HwStorStartIo</i> callback  is not synchronized with the callback to the <i>HwStorTimer</i> routine when multi-channel support is used.  The miniport must do this on its own by using a compiler interlocked intrinsic, for example using <a href="..\wdm\nf-wdm-interlockedcompareexchange.md">InterlockedCompareExchange</a>. 

A <b>HwStorTimer</b> routine is optional.

To define an <b>HwStorTimer</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorTimer</b> callback routine that is named <i>MyHwTimer</i>, use the <b>HW_TIMER</b> type as shown in this code example:

Then, implement your callback routine as follows:

The <b>HW_TIMER</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_TIMER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportnotification.md">StorPortNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_TIMER routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

