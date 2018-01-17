---
UID: NF:wdfdevice.WdfDeviceResumeIdle
title: WdfDeviceResumeIdle macro
author: windows-driver-content
description: The WdfDeviceResumeIdle method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.
old-location: wdf\wdfdeviceresumeidle.htm
old-project: wdf
ms.assetid: d63848e8-0e6a-4ad7-a147-8804869b9c9b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceResumeIdle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceResumeIdle
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
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceResumeIdle macro



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceResumeIdle</b> method informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.



## -syntax

````
VOID WdfDeviceResumeIdle(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -remarks
Every call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicestopidle.md">WdfDeviceStopIdle</a> must eventually be followed by a call to <b>WdfDeviceResumeIdle</b>, or else the device will never return to a low-power state if it again becomes idle.

Calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn932459">WdfDeviceResumeIdleWithTag</a> instead of <b>WdfDeviceResumeIdle</b> provides additional information (tag value, line number, and file name) that you can view in Microsoft debuggers.

The following code example informs the framework that the specified device is not in use and can be placed in a device low-power state if it remains idle.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/25F4EEBB-4733-498C-8704-8E015F81FE06">Debugging Power Reference Leaks in WDF</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn932459">WdfDeviceResumeIdleWithTag</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicestopidle.md">WdfDeviceStopIdle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn932460">WdfDeviceStopIdleWithTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceResumeIdle method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

