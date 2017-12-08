---
UID: NF.wdfinterrupt.WdfInterruptGetDevice
title: WdfInterruptGetDevice function
author: windows-driver-content
description: The WdfInterruptGetDevice method returns a handle to the framework device object that is associated with a specified framework interrupt object.
old-location: wdf\wdfinterruptgetdevice.htm
old-project: wdf
ms.assetid: c1e7a9ce-5794-4ed0-bb30-e3e68b0251db
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfInterruptGetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfInterruptGetDevice
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DIRQL
req.product: Windows 10 or later.
---

# WdfInterruptGetDevice function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfInterruptGetDevice</b> method returns a handle to the framework device object that is associated with a specified framework interrupt object.


## -syntax

````
WDFDEVICE WdfInterruptGetDevice(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters

### -param Interrupt [in]

A handle to a framework interrupt object.

## -returns
<b>WdfInterruptGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.

The following code example shows how an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function can obtain a pointer to driver-defined context space for the device object that an interrupt object belongs to.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfinterrupt.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DIRQL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptGetDevice method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
