---
UID: NF.video.VideoPortCreateEvent
title: VideoPortCreateEvent function
author: windows-driver-content
description: The VideoPortCreateEvent function creates an event object.
old-location: display\videoportcreateevent.htm
old-project: display
ms.assetid: bb1ef5f0-ccf3-487b-99e6-9ec733c7cd63
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: VideoPortCreateEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortCreateEvent
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# VideoPortCreateEvent function



## -description
The <b>VideoPortCreateEvent</b> function creates an event object.



## -syntax

````
VP_STATUS VideoPortCreateEvent(
  _In_  PVOID  HwDeviceExtension,
  _In_  ULONG  EventFlag,
  _In_  PVOID  Unused,
  _Out_ PEVENT *ppEvent
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param EventFlag [in]

Specifies the event type and initial event state. This can be an ORed combination of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
INITIAL_EVENT_SIGNALED

</td>
<td>
Set this flag to indicate the signaled state for the event object. Otherwise, the initial state of the event is nonsignaled.

</td>
</tr>
<tr>
<td>
 NOTIFICATION_EVENT

</td>
<td>
Set this flag to create a notification event. If this flag is not set, a synchronization event is created.

</td>
</tr>
</table>
 


### -param Unused [in]

Is currently ignored by the video port driver and must be set to <b>NULL</b>.


### -param ppEvent [out]

Pointer to the memory location at which a pointer to the event object will be returned.


## -returns
<b>VideoPortCreateEvent</b> returns NO_ERROR if the event object is successfully created.


## -remarks
When a synchronization event is set to the signaled state, a single thread that was waiting for the signaled state is released (its dispatch state transitions from waiting to ready, standby, or running), and the event is automatically reset to the nonsignaled state.

When a notification event is set to the signaled state, all threads that were waiting for the signaled state are released, and the event remains in the signaled state until it is explicitly reset to the nonsignaled state. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
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
<a href="display.videoportdeleteevent">VideoPortDeleteEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortCreateEvent function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

