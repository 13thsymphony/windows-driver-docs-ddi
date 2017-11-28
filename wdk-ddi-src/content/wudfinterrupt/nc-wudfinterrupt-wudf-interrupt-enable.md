---
UID: NC.wudfinterrupt.WUDF_INTERRUPT_ENABLE
title: WUDF_INTERRUPT_ENABLE
author: windows-driver-content
description: A driver's OnInterruptEnable event callback function enables a specified hardware interrupt.
old-location: wdf\oninterruptenable.htm
old-project: wdf
ms.assetid: 6C091427-59FF-4101-ACD6-353C959794F6
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: OnInterruptEnable
req.alt-loc: Wudfinterrupt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# WUDF_INTERRUPT_ENABLE callback



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>A driver's <i>OnInterruptEnable</i> event callback function enables a specified hardware interrupt.</p>


## -prototype

````
WUDF_INTERRUPT_ENABLE OnInterruptEnable;

HRESULT OnInterruptEnable(
  _In_ IWDFInterrupt *pInterrupt,
  _In_ IWDFDevice    *pAssociatedDevice
)
{ ... }
````


## -parameters
<dl>

### -param <i>pInterrupt</i> [in]

<dd>
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451283">IWDFInterrupt</a> interface.</p>
</dd>

### -param <i>pAssociatedDevice</i> [in]

<dd>
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface that the driver used to call <a href="https://msdn.microsoft.com/library/windows/hardware/hh451208">CreateInterrupt</a>. </p>
</dd>
</dl>

## -returns
<p>The callback function must return S_OK if the operation succeeds. Otherwise, the callback should return one of the error codes that are defined in Winerror.h.</p>

## -remarks
<p>To register an <i>OnInterruptEnable</i> callback function, your driver must place the callback function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464084">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="wdf.iwdfdevice3_createinterrupt">IWDFDevice::CreateInterrupt</a>.</p>

<p>
The framework calls the driver's <i>OnInterruptEnable</i> callback function each time the device enters its working (D0) state. Additionally, a driver can cause the framework to call the <i>OnInterruptEnable</i> callback function by calling <a href="wdf.iwdfinterrupt_enable">IWDFInterrupt::Enable</a>.</p>

<p>
Before calling the <i>OnInterruptEnable</i> callback function, the framework acquires the user-mode interrupt lock.</p>

<p> 
After calling the <i>OnInterruptEnable</i> callback function, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439750">OnD0EntryPostInterruptsEnabled</a> event callback function.
</p>

<p>
For more information about handling interrupts in UMDF drivers, see <a href="wdf.accessing_hardware_and_handling_interrupts">Accessing Hardware and Handling Interrupts</a>.</p>

<p>The function type is declared in <i>Wudfinterrupt.h</i>, as follows.</p>

<p>To define an <i>OnInterruptEnable</i> callback function that is named <i>MyInterruptEnable</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

<p>To register an <i>OnInterruptEnable</i> callback function, your driver must place the callback function's address in a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464084">WUDF_INTERRUPT_CONFIG</a> structure before calling <a href="wdf.iwdfdevice3_createinterrupt">IWDFDevice::CreateInterrupt</a>.</p>

<p>
The framework calls the driver's <i>OnInterruptEnable</i> callback function each time the device enters its working (D0) state. Additionally, a driver can cause the framework to call the <i>OnInterruptEnable</i> callback function by calling <a href="wdf.iwdfinterrupt_enable">IWDFInterrupt::Enable</a>.</p>

<p>
Before calling the <i>OnInterruptEnable</i> callback function, the framework acquires the user-mode interrupt lock.</p>

<p> 
After calling the <i>OnInterruptEnable</i> callback function, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439750">OnD0EntryPostInterruptsEnabled</a> event callback function.
</p>

<p>
For more information about handling interrupts in UMDF drivers, see <a href="wdf.accessing_hardware_and_handling_interrupts">Accessing Hardware and Handling Interrupts</a>.</p>

<p>The function type is declared in <i>Wudfinterrupt.h</i>, as follows.</p>

<p>To define an <i>OnInterruptEnable</i> callback function that is named <i>MyInterruptEnable</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.11</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfinterrupt.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh464084">WUDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="wdf.iwdfdevice3_createinterrupt">IWDFDevice::CreateInterrupt</a>
</dt>
<dt>
<a href="..\wudfinterrupt\nc-wudfinterrupt-wudf-interrupt-disable.md">OnInterruptDisable</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_INTERRUPT_ENABLE callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
