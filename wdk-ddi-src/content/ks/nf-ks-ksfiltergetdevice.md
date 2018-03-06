---
UID: NF:ks.KsFilterGetDevice
title: KsFilterGetDevice function
author: windows-driver-content
description: The KsFilterGetDevice function returns the AVStream device to which Filter belongs.
old-location: stream\ksfiltergetdevice.htm
old-project: stream
ms.assetid: f3abb5e4-6711-47bb-82b5-7ef838d49258
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterGetDevice, KsFilterGetDevice function [Streaming Media Devices], avfunc_279c1429-d19f-426c-a1e3-8507f97092ae.xml, ks/KsFilterGetDevice, stream.ksfiltergetdevice
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
req.lib: NtosKrnl.exe
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
-	KsFilterGetDevice
product: Windows
targetos: Windows
req.typenames: 
---


# KsFilterGetDevice function
The<b> KsFilterGetDevice </b>function returns the AVStream device to which <i>Filter</i> belongs.

## Syntax

````
PKSDEVICE __inline KsFilterGetDevice(
  _In_ PKSFILTER Filter
);
````

## Parameters

`Filter`

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to find the owning AVStream device.


## Return Value

<b>KsFilterGetDevice</b> returns a pointer to the AVStream <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure to which <i>Filter</i> belongs.

## Remarks

This call is an inline function call to <a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetDevice function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>