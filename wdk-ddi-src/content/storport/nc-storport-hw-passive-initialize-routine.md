---
UID: NC.storport.HW_PASSIVE_INITIALIZE_ROUTINE
title: HW_PASSIVE_INITIALIZE_ROUTINE
author: windows-driver-content
description: The HwStorPassiveInitializeRoutine callback routine is called after the HwStorInitialize routine when the current IRQL is at PASSIVE_LEVEL.
old-location: storage\hwstorpassiveinitializeroutine.htm
old-project: storage
ms.assetid: 70f65a4e-0a98-4135-bb38-530c729538a3
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
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
req.alt-api: HwStorPassiveInitializeRoutine
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
req.irql: PASSIVE_LEVEL (See Remarks section.)
req.iface: 
req.product: Windows 10 or later.
---

# HW_PASSIVE_INITIALIZE_ROUTINE callback



## -description
<p>The <b>HwStorPassiveInitializeRoutine</b> callback routine is called after the <a href="storage.hwstorinitialize">HwStorInitialize</a> routine when the current IRQL is at PASSIVE_LEVEL. The <b>HwStorPassiveInitializeRoutine</b> callback is set by calling the <a href="..\storport\nf-storport-storportenablepassiveinitialization.md">StorPortEnablePassiveInitialization</a> routine. Initializing of the miniport's deferred procedure calls (DPCs) occurs in the <b>HwStorPassiveInitializeRoutine</b> callback.</p>


## -prototype

````
HW_PASSIVE_INITIALIZE_ROUTINE HwStorPassiveInitializeRoutine;

BOOLEAN HwStorPassiveInitializeRoutine(
   IN PVOID HwDeviceExtension
)
{ ... }
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>A pointer to a per-adapter storage area. </p>
</dd>
</dl>

## -returns
<p>The <b>HwStorPassiveInitializeRoutine</b> routine returns <b>TRUE</b> if the miniport successfully initialized the processing of DPCs, or <b>FALSE</b> if the initialization process failed. </p>

## -remarks
<p>The <b>HwStorPassiveInitializeRoutine</b> routine should initialize any DPCs that the miniport driver will use. The port driver calls <b>HwStorPassiveInitializeRoutine</b> at PASSIVE_LEVEL without any spin locks held. Interrupts are enabled while this routine is called.</p>

<p>The name <b>HwStorPassiveInitializeRoutine</b> is just a placeholder. The actual prototype for this callback routine is defined in <i>storport.h</i>as follows:</p>

<p>The port driver calls the <b>HwStorPassiveInitializeRoutine</b> routine at PASSIVE IRQL without acquiring any spin locks.</p>

<p>To define an <b>HwStorPassiveInitializeRoutine</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p> For example, to define a <b>HwStorPassiveInitializeRoutine</b> callback routine that is named <i>MyHwPassiveInitialize</i>, use the <b>HW_PASSIVE_INITIALIZE_ROUTINE</b> type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The <b>HW_PASSIVE_INITIALIZE_ROUTINE</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_PASSIVE_INITIALIZE_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (See Remarks section.)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportenablepassiveinitialization.md">StorPortEnablePassiveInitialization</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorPassiveInitializeRoutine routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
