---
UID: NC.storport.HW_CLEANUP_TRACING
title: HW_CLEANUP_TRACING
author: windows-driver-content
description: The HwStorCleanupTracing callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.
old-location: storage\hwstorcleanuptracing.htm
old-project: storage
ms.assetid: 878a7c4f-8584-4de2-9a32-f1c358d9b27f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
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
req.alt-api: HwStorCleanupTracing
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
req.product: Windows 10 or later.
---

# HW_CLEANUP_TRACING callback



## -description
The <b>HwStorCleanupTracing</b> callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.


## -prototype

````
HW_CLEANUP_TRACING HwStorCleanupTracing;

VOID HwStorCleanupTracing(
   IN PVOID Arg1
)
{ ... }
````


## -parameters

### -param Arg1 

A pointer to the driver object.

## -returns
None

## -remarks
The name <b>HwStorCleanupTracing</b> is  placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

The port driver calls the Storport virtual miniport's <b>HwStorCleanupTracing</b> at PASSIVE_LEVEL.

To define an <b>HwStorCleanupTracing</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorCleanupTracing</b> callback routine that is named <i>MyHwCleanupTracing</i>, use the <b>HW_CLEANUP_TRACING</b> type as shown in this code example:

Then, implement your callback routine as follows:

The <b>HW_CLEANUP_TRACING</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_CLEANUP_TRACING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

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