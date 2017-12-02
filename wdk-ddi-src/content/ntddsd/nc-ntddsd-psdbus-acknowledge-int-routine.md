---
UID: NC.ntddsd.PSDBUS_ACKNOWLEDGE_INT_ROUTINE
title: PSDBUS_ACKNOWLEDGE_INT_ROUTINE
author: windows-driver-content
description: The PSDBUS_ACKNOWLEDGE_INT_ROUTINE prototype declares the routine that a Secure Digital (SD) device driver must call to acknowledge to the bus driver that it has finished processing the interrupt.
old-location: sd\psdbus_acknowledge_int_routine.htm
old-project: SD
ms.assetid: b3d23404-2d55-4a37-8c4c-d857c5307f18
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: STORAGE_DIAGNOSTIC_MP_REQUEST, STORAGE_DIAGNOSTIC_MP_REQUEST, *PSTORAGE_DIAGNOSTIC_MP_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddsd.h
req.include-header: Ntddsd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AcknowledgeInterrupt
req.alt-loc: ntddsd.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL (See Remarks section.)
req.iface: 
---

# PSDBUS_ACKNOWLEDGE_INT_ROUTINE callback



## -description
<p>The PSDBUS_ACKNOWLEDGE_INT_ROUTINE prototype declares the routine that a Secure Digital (SD) device driver must call to acknowledge to the bus driver that it has finished processing the interrupt.</p>


## -prototype

````
PSDBUS_ACKNOWLEDGE_INT_ROUTINE AcknowledgeInterrupt;

NTSTATUS AcknowledgeInterrupt(
  _In_ PVOID Context
)
{ ... }
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>Contains the interface context that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine returns in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_UNSUCCESSFUL if the operation succeeds, or the appropriate error message if the operation fails.</p>

## -remarks
<p>When an SD device asserts an interrupt, the bus driver disables the interrupt that the device asserted to allow the device driver to perform I/O at IRQL &lt;=DISPATCH_LEVEL. When the device driver's callback routine, which is equivalent to an interrupt service routine, finishes clearing the interrupt, it should acknowledge that it has finished interrupt processing so that the bus driver can re-enable the disabled interrupt. </p>

<p>Traditionally, drivers acknowledge interrupts by simply returning the appropriate value from the interrupt service routine (ISR). When drivers rely on this method, they are constrained to acknowledge interrupts in the order that they receive them. An SD card driver, on the other hand, is <i>not </i>constrained to acknowledge interrupts in the order that they are received. Typically, a driver for an SD card might report several interrupts to the bus driver (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537617">PSDBUS_CALLBACK_ROUTINE</a>) before acknowledging any of them. Under normal operating conditions, an SD card driver defers acknowledging an interrupt until the interrupt state on the device has cleared.</p>

<p>The caller must be running at IRQL &lt;= DISPATCH_LEVEL when it acknowledges that it has finished processing an interrupt.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddsd.h (include Ntddsd.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL (See Remarks section.)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20PSDBUS_ACKNOWLEDGE_INT_ROUTINE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
