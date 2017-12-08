---
UID: NF.wdfinterrupt.WDF_INTERRUPT_CONFIG_INIT
title: WDF_INTERRUPT_CONFIG_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_CONFIG_INIT function initializes a WDF_INTERRUPT_CONFIG structure.
old-location: wdf\wdf_interrupt_config_init.htm
old-project: wdf
ms.assetid: e81ec3da-a863-467f-82ec-1fa7ee6401b1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_INTERRUPT_CONFIG_INIT
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
req.alt-api: WDF_INTERRUPT_CONFIG_INIT
req.alt-loc: wdfinterrupt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# WDF_INTERRUPT_CONFIG_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_INTERRUPT_CONFIG_INIT</b> function initializes a <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.


## -syntax

````
VOID WDF_INTERRUPT_CONFIG_INIT(
  _Out_    PWDF_INTERRUPT_CONFIG Configuration,
  _In_     PFN_WDF_INTERRUPT_ISR EvtInterruptIsr,
  _In_opt_ PFN_WDF_INTERRUPT_DPC EvtInterruptDpc
);
````


## -parameters

### -param Configuration [out]

A pointer to a <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.

### -param EvtInterruptIsr [in]

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function.

### -param EvtInterruptDpc [in, optional]

A pointer to the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function, or <b>NULL</b>.

## -returns
None

## -remarks
The <b>WDF_INTERRUPT_CONFIG_INIT</b> function zeros the specified <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure and sets its <b>Size</b> member to the structure's size. It also sets the structure's <b>ShareVector</b> member to <b>WdfUseDefault</b> and stores the specified callback function pointers. Finally, it sets the <b>ReportInactiveOnPowerDown</b>  member of the specified <b>WDF_INTERRUPT_CONFIG</b> structure to <b>WdfDefault</b>.

For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.

For a code example that uses <b>WDF_INTERRUPT_CONFIG_INIT</b>, see <a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a>.

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
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>
</dt>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_CONFIG_INIT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
