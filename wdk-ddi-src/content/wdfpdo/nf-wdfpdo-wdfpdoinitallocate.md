---
UID: NF:wdfpdo.WdfPdoInitAllocate
title: WdfPdoInitAllocate function
author: windows-driver-content
description: The WdfPdoInitAllocate method allocates a WDFDEVICE_INIT structure for a framework-based bus driver, which the bus driver uses when reporting a new device.
old-location: wdf\wdfpdoinitallocate.htm
old-project: wdf
ms.assetid: 86e48354-d4cd-4ad0-a6bd-e8ba662075d8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_bc23c37b-d595-4672-ad92-4a29aea9c2dd.xml, WdfPdoInitAllocate, WdfPdoInitAllocate method, kmdf.wdfpdoinitallocate, wdf.wdfpdoinitallocate, wdfpdo/WdfPdoInitAllocate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: AddPdoToStaticChildList, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate, PdoInitFreeDeviceCreateType2, PdoInitFreeDeviceCreateType4
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfPdoInitAllocate
product: Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---


# WdfPdoInitAllocate function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoInitAllocate</b> method allocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure for a framework-based bus driver, which the bus driver uses when reporting a new device.

## Syntax

```
PWDFDEVICE_INIT WdfPdoInitAllocate(
  WDFDEVICE ParentDevice
);
```

## Parameters

`ParentDevice`

A handle to a framework device object that represents the parent device of the new device. The framework device object must represent a functional device object (FDO).


## Return Value

If the operation succeeds, the method returns a pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. Otherwise, the method returns <b>NULL</b>.

## Remarks

If a bus driver uses static enumeration, it reports a new device by:

<ol>
<li>
Calling <b>WdfPdoInitAllocate</b> to allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.

</li>
<li>
Calling <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">framework device object initialization methods</a> and <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn265631">framework PDO initialization methods</a>, as needed, to initialize the WDFDEVICE_INIT structure. If a call to one of these methods fails, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546050">WdfDeviceInitFree</a>. 

</li>
<li>
Calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> to create a framework device object, supplying the initialized WDFDEVICE_INIT structure as input.

</li>
</ol>
For more information about static enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

For a code example that uses <b>WdfPdoInitAllocate</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547225">WdfFdoAddStaticChild</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfpdo.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | AddPdoToStaticChildList, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate, PdoInitFreeDeviceCreateType2, PdoInitFreeDeviceCreateType4 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>