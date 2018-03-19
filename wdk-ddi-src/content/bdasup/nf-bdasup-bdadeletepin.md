---
UID: NF:bdasup.BdaDeletePin
title: BdaDeletePin function
author: windows-driver-content
description: The BdaDeletePin function deletes a pin from the specified filter.
old-location: stream\bdadeletepin.htm
old-project: stream
ms.assetid: 32ff70d7-980c-4c80-8ebc-af2121bc64df
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: BdaDeletePin, BdaDeletePin function [Streaming Media Devices], bdaref_36a08eca-6cfb-4647-8252-05b6c8e0b8e1.xml, bdasup/BdaDeletePin, stream.bdadeletepin
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
-	BdaDeletePin
product: Windows
targetos: Windows
req.typenames: KSP_BDA_NODE_PIN, *PKSP_BDA_NODE_PIN
---


# BdaDeletePin function
The <b>BdaDeletePin</b> function deletes a pin from the specified filter.

## Syntax

````
NTSTATUS BdaDeletePin(
  _In_      PKSFILTER pKSFilter,
  _Out_opt_ PULONG    pulPinId
);
````

## Parameters

`pKSFilter`

Points to the filter in which to delete a pin.

`pulPinId`

Points to a variable that contains the identifier for the pin to delete.


## Return Value

Returns STATUS_SUCCESS or an appropriate error code.

## Remarks

A BDA minidriver calls the <a href="..\bdasup\nf-bdasup-bdamethoddeletepin.md">BdaMethodDeletePin</a> function when the network provider dynamically deletes a pin using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a> method set. If a BDA minidriver must delete a pin without relying on the network provider, the BDA minidriver should call the <b>BdaDeletePin</b> function directly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.  |
| **Target Platform** | Desktop |
| **Header** | bdasup.h (include Bdasup.h) |
| **Library** | Bdasup.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\bdasup\nf-bdasup-bdamethoddeletepin.md">BdaMethodDeletePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563415">KSMETHOD_BDA_DELETE_PIN_FACTORY</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



<a href="..\bdasup\nf-bdasup-bdacreatepin.md">BdaCreatePin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563404">KSMETHODSETID_BdaDeviceConfiguration</a>