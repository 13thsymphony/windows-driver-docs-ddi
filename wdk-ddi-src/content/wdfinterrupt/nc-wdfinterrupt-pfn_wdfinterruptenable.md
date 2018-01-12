---
UID: NC:wdfinterrupt.PFN_WDFINTERRUPTENABLE
title: PFN_WDFINTERRUPTENABLE function
author: windows-driver-content
description: The WdfInterruptEnable method enables a specified device interrupt by calling the driver's EvtInterruptEnable callback function.
old-location: wdf\wdfinterruptenable.htm
old-project: wdf
ms.assetid: e2ffab7f-b6bf-4707-9a3d-9619330b2af1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFINTERRUPTENABLE
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
req.alt-api: WdfInterruptEnable
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFINTERRUPTENABLE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptEnable</b> method enables a specified device interrupt by calling the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a> callback function.



## -syntax

````
VOID WdfInterruptEnable(
  _In_ WDFINTERRUPT Interrupt
);
````


## -parameters

### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Most framework-based drivers don't need to call <b>WdfInterruptEnable</b>, because the framework calls the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a> callback function each time the device enters its working (D0) state.

For <a href="wdf.supporting_passive_level_interrupts">passive-level interrupt objects</a>, the framework calls <b>WdfInterruptEnable</b> at PASSIVE_LEVEL.

Do not call <b>WdfInterruptEnable</b> from an arbitrary thread context,  such as a <a href="wdf.request_handlers">request handler</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

The following code example enables the device interrupt that is associated with a specified interrupt object.


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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfinterrupt\nf-wdfinterrupt-wdfinterruptdisable.md">WdfInterruptDisable</a>
</dt>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfInterruptEnable method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

