---
UID: NF:wdfdevice.WdfDeviceGetCharacteristics
title: WdfDeviceGetCharacteristics function
author: windows-driver-content
description: The WdfDeviceGetCharacteristics method returns device characteristics for a specified device.
old-location: wdf\wdfdevicegetcharacteristics.htm
old-project: wdf
ms.assetid: 985dcde1-5643-4c35-9096-44b076a1dd51
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceGetCharacteristics, wdfdevice/WdfDeviceGetCharacteristics, kmdf.wdfdevicegetcharacteristics, WdfDeviceGetCharacteristics method, PFN_WDFDEVICEGETCHARACTERISTICS, DFDeviceObjectGeneralRef_b6e7566f-59b1-46ee-ab3d-45fa7316336e.xml, wdf.wdfdevicegetcharacteristics
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceGetCharacteristics
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceGetCharacteristics function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceGetCharacteristics</b> method returns device characteristics for a specified device.

## Syntax

````
ULONG WdfDeviceGetCharacteristics(
  _In_ WDFDEVICE Device
);
````

## Parameters

`Device`

A handle to a framework device object.


## Return Value

A bitwise OR of system-defined constants that represent device characteristics. For more information, see the <b>Characteristics</b> member of the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetcharacteristics.md">WdfDeviceInitSetCharacteristics</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetcharacteristics.md">WdfDeviceSetCharacteristics</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetCharacteristics method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>