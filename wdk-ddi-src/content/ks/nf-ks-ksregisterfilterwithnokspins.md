---
UID: NF:ks.KsRegisterFilterWithNoKSPins
title: KsRegisterFilterWithNoKSPins function
author: windows-driver-content
description: The KsRegisterFilterWithNoKSPins function registers with DirectShow filters that have no kernel streaming pins and, therefore, do not stream in kernel mode.
old-location: stream\ksregisterfilterwithnokspins.htm
old-project: stream
ms.assetid: 4ad768c9-211d-4370-b6d3-6d88b223fe48
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsRegisterFilterWithNoKSPins, KsRegisterFilterWithNoKSPins function [Streaming Media Devices], avfunc_c9fc5273-7fd9-41d5-9ac4-5033ed757b7c.xml, ks/KsRegisterFilterWithNoKSPins, stream.ksregisterfilterwithnokspins
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsRegisterFilterWithNoKSPins
product: Windows
targetos: Windows
req.typenames: 
---


# KsRegisterFilterWithNoKSPins function
The<b> KsRegisterFilterWithNoKSPins </b>function registers with DirectShow filters that have no kernel streaming pins and, therefore, do not stream in kernel mode.

## Syntax

```
KSDDKAPI NTSTATUS KsRegisterFilterWithNoKSPins(
  PDEVICE_OBJECT DeviceObject,
  const GUID     *InterfaceClassGUID,
  ULONG          PinCount,
  BOOL           *PinDirection,
  KSPIN_MEDIUM   *MediumList,
  GUID           *CategoryList
);
```

## Parameters

`DeviceObject`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure corresponding to the device to which to register the filter.

`InterfaceClassGUID`

A pointer to the GUID representing the class to register. For instance, this would point to KSCATEGORY_TVTUNER for a TvTuner filter.

`PinCount`

The count of the number of pins on the filter.

`PinDirection`

A pointer to the first element of an array of Boolean values indicating pin direction for each pin on the filter. Output pins are <b>TRUE</b>; input pins are <b>FALSE</b>. This array must be <i>PinCount</i> in length.

`MediumList`

A pointer to the first element of an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> structures defining the mediums for each pin on the filter. This array must be <i>PinCount</i> in length.

`CategoryList`

A pointer to the first element of an array of GUIDs defining the categories for each pin on the filter. If this parameter is present, it must be <i>PinCount</i> in length.


## Return Value

Returns success or failure of creating the FilterData key in the registry.

## Remarks

Use<b> KsRegisterFilterWithNoKSPins</b> to register TvTuners, Crossbars, and similar components. <b>KsRegisterFilterWithNoKSPins</b> creates a new registry key, <b>FilterData</b>, that contains the mediums, and optionally the categories, for each pin on the filter.

This function is only used to register filters that have no corresponding kernel pins. If successful, <b>KsRegisterFilterWithNoKSPins</b> creates a key in the registry that can be then used by DirectShow.

If writing a BDA minidriver, consider using <a href="https://msdn.microsoft.com/library/windows/hardware/ff562540">KsFilterFactoryUpdateCacheData</a> instead of this routine. See details on the reference page for <b>KsFilterFactoryUpdateCacheData</b>.

For more information, see <a href="https://msdn.microsoft.com/fd436406-311b-4537-994d-fbd8d92d4673">AVStream Descriptors</a> and <a href="https://msdn.microsoft.com/666d6efb-93ec-43f3-87c5-ea1a3983bfd0">Initializing an AVStream Minidriver</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562540">KsFilterFactoryUpdateCacheData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562550">KsFilterRegisterPowerCallbacks</a>