---
UID: NF:ks.KsGetDeviceForDeviceObject
title: KsGetDeviceForDeviceObject function
author: windows-driver-content
description: The KsGetDeviceForDeviceObject function returns the AVStream device structure for a given functional device object.
old-location: stream\ksgetdevicefordeviceobject.htm
old-project: stream
ms.assetid: 2fe72d9d-1423-4db9-be38-f2bca7dbc56d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetDeviceForDeviceObject, KsGetDeviceForDeviceObject function [Streaming Media Devices], avfunc_2bc27061-02ce-488f-94b4-087e9f264614.xml, ks/KsGetDeviceForDeviceObject, stream.ksgetdevicefordeviceobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGetDeviceForDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsGetDeviceForDeviceObject function
The<b> KsGetDeviceForDeviceObject</b> function returns the AVStream device structure for a given functional device object.

## Syntax

```
KSDDKAPI PKSDEVICE KsGetDeviceForDeviceObject(
  PDEVICE_OBJECT FunctionalDeviceObject
);
```

## Parameters

`FunctionalDeviceObject`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> for which to return the corresponding <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure.


## Return Value

<b>KsGetDeviceForDeviceObject</b> returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure corresponding to <i>FunctionalDeviceObject</i>. It returns <b>NULL</b> if <i>FunctionalDeviceObject</i> is a child PDO.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562620">KsGetFilterFromFileObject</a>