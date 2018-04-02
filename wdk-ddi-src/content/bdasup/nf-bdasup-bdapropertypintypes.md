---
UID: NF:bdasup.BdaPropertyPinTypes
title: BdaPropertyPinTypes function
author: windows-driver-content
description: The BdaPropertyPinTypes function retrieves a list of pin types in a template topology.
old-location: stream\bdapropertypintypes.htm
old-project: stream
ms.assetid: 155aafd7-0d26-47b1-9401-9d780e393e03
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BdaPropertyPinTypes, BdaPropertyPinTypes function [Streaming Media Devices], bdaref_38003a0c-ac8f-4249-b7b1-a4979f05b7ab.xml, bdasup/BdaPropertyPinTypes, stream.bdapropertypintypes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Bdasup.lib
-	Bdasup.dll
api_name:
-	BdaPropertyPinTypes
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---


# BdaPropertyPinTypes function
The <b>BdaPropertyPinTypes</b> function retrieves a list of pin types in a template topology.

## Syntax

```
NTSTATUS BdaPropertyPinTypes(
  PIRP        pIrp,
  PKSPROPERTY pKSProperty,
  ULONG       *pulProperty
);
```

## Parameters

`pIrp`

TBD

`pKSProperty`

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.

`pulProperty`

Points to an array that receives the list of pin types.


## Return Value

Returns STATUS_SUCCESS or an appropriate error code.

## Remarks

A BDA minidriver calls the <b>BdaPropertyPinTypes</b> function to retrieve the list of pin types after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564352">KSPROPERTY_BDA_PIN_TYPES</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyPinTypes</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.  |
| **Target Platform** | Desktop |
| **Header** | bdasup.h (include Bdasup.h) |
| **Library** | Bdasup.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564352">KSPROPERTY_BDA_PIN_TYPES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>