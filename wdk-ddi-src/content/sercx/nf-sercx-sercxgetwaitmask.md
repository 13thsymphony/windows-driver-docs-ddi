---
UID: NF.sercx.SerCxGetWaitMask
title: SerCxGetWaitMask function
author: windows-driver-content
description: The SerCxGetWaitMask method returns the event wait mask for the wait operation that is currently pending.
old-location: serports\sercxgetwaitmask.htm
old-project: serports
ms.assetid: 57A8E522-D787-4663-B2E3-46E8430388B7
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCxGetWaitMask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCxGetWaitMask
req.alt-loc: 1.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# SerCxGetWaitMask function



## -description
The <b>SerCxGetWaitMask</b> method returns the event wait mask for the wait operation that is currently pending.


## -syntax

````
ULONG SerCxGetWaitMask(
  [in] WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.

## -returns
<b>SerCxGetWaitMask</b> returns a wait mask that specifies the events that a client (application or peripheral driver)  selected to trigger completion of the wait operation that is currently pending. If no wait operation is pending, this method returns the null wait mask, 0x0000. For more information, see the following Remarks section.

## -remarks
The serial controller driver calls <b>SerCxGetWaitMask</b> to obtain the wait mask to use for a pending wait operation. Typically, the controller driver calls this method from the <a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a> callback function.

The wait mask indicates the types of events that can trigger completion of a wait operation. Each bit in the wait mask represents a particular type of event. A bit is set in the wait mask if the corresponding event will trigger completion of a wait operation. For more information about the meaning of the bits in the wait mask, see <a href="serports.serial_ev_xxx">SERIAL_EV_XXX</a>.

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
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>1.0\Sercx.h</dt>
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
<dt>
<a href="..\sercx\nc-sercx-evt_sercx_waitmask.md">EvtSerCxWaitmask</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>
</dt>
<dt>
<a href="serports.serial_ev_xxx">SERIAL_EV_XXX</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxGetWaitMask method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
