---
UID: NF:wdm.IoAttachDeviceToDeviceStack
title: IoAttachDeviceToDeviceStack function
author: windows-driver-content
description: The IoAttachDeviceToDeviceStack routine attaches the caller's device object to the highest device object in the chain and returns a pointer to the previously highest device object.
old-location: kernel\ioattachdevicetodevicestack.htm
old-project: kernel
ms.assetid: 6377f980-dd56-4bef-91e7-7557866132d6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoAttachDeviceToDeviceStack, IoAttachDeviceToDeviceStack routine [Kernel-Mode Driver Architecture], k104_18c6aeef-4362-49f9-88a3-6d2a970eb0d7.xml, kernel.ioattachdevicetodevicestack, wdm/IoAttachDeviceToDeviceStack
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: AddDevice, PnpSameDeviceObject, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoAttachDeviceToDeviceStack
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoAttachDeviceToDeviceStack function
The <b>IoAttachDeviceToDeviceStack</b> routine attaches the caller's device object to the highest device object in the chain and returns a pointer to the previously highest device object.

## Syntax

````
PDEVICE_OBJECT IoAttachDeviceToDeviceStack(
  _In_ PDEVICE_OBJECT SourceDevice,
  _In_ PDEVICE_OBJECT TargetDevice
);
````

## Parameters

`SourceDevice`

Pointer to the caller-created device object.

`TargetDevice`

Pointer to another driver's device object, such as a pointer returned by a preceding call to <a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a>.


## Return Value

<b>IoAttachDeviceToDeviceStack</b> returns a pointer to the device object to which the <i>SourceDevice</i> was attached. The returned device object pointer can differ from <i>TargetDevice</i> if <i>TargetDevice</i> had additional drivers layered on top of it.

<b>IoAttachDeviceToDeviceStack</b> returns <b>NULL</b> if it could not attach the device object because, for example, the target device was being unloaded.

## Remarks

<b>IoAttachDeviceToDeviceStack</b> establishes layering between drivers so that the same IRPs are sent to each driver in the chain.

An intermediate driver can use this routine during initialization to attach its own device object to another driver's device object. Subsequent I/O requests sent to <i>TargetDevice</i> are sent first to the intermediate driver.

This routine sets the <b>AlignmentRequirement</b> in <i>SourceDevice</i>  to the value in the next-lower device object and sets the <b>StackSize</b> to the value in the next-lower-object plus one.

A driver writer must take care to call this routine <u>before</u> any drivers that must layer on top of their driver. <b>IoAttachDeviceToDeviceStack</b> attaches <i>SourceDevice</i> to the highest device object currently layered in the chain and has no way to determine whether drivers are being layered in the correct order.

A driver that acquired a pointer to the target device by calling <a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a> should call <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> with the file object pointer that was returned by <b>IoGetDeviceObjectPointer</b> to release its reference to the file object before it detaches its own device object, for example, when such a higher-level driver is unloaded.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | AddDevice, PnpSameDeviceObject, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-iogetdeviceobjectpointer.md">IoGetDeviceObjectPointer</a>



<a href="..\wdm\nf-wdm-iodetachdevice.md">IoDetachDevice</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\wdm\nf-wdm-ioattachdevice.md">IoAttachDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAttachDeviceToDeviceStack routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>