---
UID: NF:ks.KsFilterFactoryGetParentDevice
title: KsFilterFactoryGetParentDevice function
author: windows-driver-content
description: The KsFilterFactoryGetParentDevice function returns the parent device of the given filter factory.
old-location: stream\ksfilterfactorygetparentdevice.htm
old-project: stream
ms.assetid: ac1d10dc-d3cb-4a83-9f52-34ea90d2193b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFilterFactoryGetParentDevice, stream.ksfilterfactorygetparentdevice, KsFilterFactoryGetParentDevice function [Streaming Media Devices], KsFilterFactoryGetParentDevice, avfunc_35d9d582-f7d6-4c1f-8998-a6664527db2c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsFilterFactoryGetParentDevice
product: Windows
targetos: Windows
req.typenames: 
---


# KsFilterFactoryGetParentDevice function
The<b> KsFilterFactoryGetParentDevice</b> function returns the parent device of the given filter factory.

## Syntax

````
PKSDEVICE __inline KsFilterFactoryGetParentDevice(
  _In_ PKSFILTERFACTORY FilterFactory
);
````

## Parameters

`FilterFactory`

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure for which to return the parent device.


## Return Value

<b>KsFilterFactoryGetParentDevice</b> returns a pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the parent device of the filter factory. This is the AVStream device to which the filter factory belongs.

## Remarks

This call is an inline function call to <a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>



<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryGetParentDevice function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>