---
UID: NC:wdfdevice.PFN_WDFDEVICEGETCHARACTERISTICS
title: PFN_WDFDEVICEGETCHARACTERISTICS function
author: windows-driver-content
description: The WdfDeviceGetCharacteristics method returns device characteristics for a specified device.
old-location: wdf\wdfdevicegetcharacteristics.htm
old-project: wdf
ms.assetid: 985dcde1-5643-4c35-9096-44b076a1dd51
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEGETCHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceGetCharacteristics
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# PFN_WDFDEVICEGETCHARACTERISTICS function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetCharacteristics</b> method returns device characteristics for a specified device.



## -syntax

````
ULONG WdfDeviceGetCharacteristics(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -returns
A bitwise OR of system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.

The following code example obtains a device's characteristics.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetcharacteristics.md">WdfDeviceInitSetCharacteristics</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetcharacteristics.md">WdfDeviceSetCharacteristics</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetCharacteristics method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

