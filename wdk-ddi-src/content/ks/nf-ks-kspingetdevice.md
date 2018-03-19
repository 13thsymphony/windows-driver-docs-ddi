---
UID: NF:ks.KsPinGetDevice
title: KsPinGetDevice function
author: windows-driver-content
description: The KsPinGetDevice function returns the AVStream device to which Pin belongs.
old-location: stream\kspingetdevice.htm
old-project: stream
ms.assetid: 965aa806-90cc-4c82-a126-42ae433cba3b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinGetDevice, KsPinGetDevice function [Streaming Media Devices], avfunc_09495aa3-2bed-4093-a989-2ae444f1c372.xml, ks/KsPinGetDevice, stream.kspingetdevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsPinGetDevice
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinGetDevice function
The<b> KsPinGetDevice </b>function returns the AVStream device to which <i>Pin</i> belongs.

## Syntax

````
PKSDEVICE __inline KsPinGetDevice(
  _In_ PKSPIN Pin
);
````

## Parameters

`Pin`

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the pin for which to return the owning AVStream device.


## Return Value

<b>KsPinGetDevice </b>returns a pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the AVStream device to which <i>Pin</i> belongs.

## Remarks

This call is an inline function call to <a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ns-ks-_ksdevice_descriptor.md">KSDEVICE_DESCRIPTOR</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>