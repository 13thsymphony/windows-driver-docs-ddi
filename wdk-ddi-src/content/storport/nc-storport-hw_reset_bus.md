---
UID: NC.storport.HW_RESET_BUS
title: HW_RESET_BUS
author: windows-driver-content
description: The HwStorResetBus routine is called by the port driver to clear error conditions.
old-location: storage\hwstorresetbus.htm
old-project: storage
ms.assetid: fda5291c-dd4e-4aa1-8dac-65cf4c4306ab
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
req.alt-api: HwStorResetBus
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
req.irql: DISPATCH_LEVEL (See Remarks section.)
req.product: Windows 10 or later.
---

# HW_RESET_BUS callback



## -description
The <b>HwStorResetBus</b> routine is called by the port driver to clear error conditions.


## -prototype

````
HW_RESET_BUS HwStorResetBus;

BOOLEAN HwStorResetBus(
   IN PVOID DeviceExtension,
   IN ULONG PathId
)
{ ... }
````


## -parameters

### -param DeviceExtension 

A pointer to the miniport driver's per HBA storage area. 

### -param PathId 

Identifies the SCSI bus to be reset. 

## -returns
If the bus is successfully reset, <b>HwStorResetBus</b> returns <b>TRUE</b>. 

## -remarks
The name <b>HwStorResetBus</b> is just a placeholder. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

The port driver pauses all device IO queues for the adapter and then calls the <b>HwStorResetBus</b> routine at IRQL DISPATCH_LEVEL after acquiring the StartIo spin lock.  A miniport driver is responsible for completing SRBs received by <a href="storage.hwstorstartio">HwStorStartIo</a> for <i>PathId</i> during this routine and setting their status to SRB_STATUS_BUS_RESET if necessary.

In addition to the StartIo spin lock being taken and subsequently released after <b>HwStorResetBus</b> returns, if the miniport has requested multiple channel support through PERF_CONFIGURATION_DATA, all channel tokens will be taken and, on return of the callback, released.  This ensures that no IO’s are dispatched to <a href="storage.hwstorstartio">HwStorStartIo</a> during the reset bus phase.

To define an <b>HwStorResetBus</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorResetBus</b> callback routine that is named <i>MyHwResetBus</i>, use the <b>HW_RESET_BUS</b> type as shown in this code example:

Then, implement your callback routine as follows:

The <b>HW_RESET_BUS</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_RESET_BUS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

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
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
DISPATCH_LEVEL (See Remarks section.)
</td>
</tr>
</table>