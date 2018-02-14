---
UID: NF:ks.KsGetParent
title: KsGetParent function
author: windows-driver-content
description: The KsGetParent function acquires the parent of the given object.
old-location: stream\ksgetparent.htm
old-project: stream
ms.assetid: d7804745-295f-491a-80f4-84441598bbf4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksgetparent, avfunc_da3c1932-98b1-4f29-8b5a-4663077759e9.xml, KsGetParent, ks/KsGetParent, KsGetParent function [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetParent
product: Windows
targetos: Windows
req.typenames: 
---


# KsGetParent function
The<b> KsGetParent</b> function acquires the parent of the given object.

## Syntax

````
PVOID KsGetParent(
  _In_ PVOID Object
);
````

## Parameters

`Object`

A pointer to the AVStream object for which to find the parent. Must be a pointer to one of the following types: <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>, <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>, <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>, or <a href="..\ks\ns-ks-_kspin.md">KSPIN</a>. Callers must manually typecast the object to a PVOID.


## Return Value

<b>KsGetParent</b> returns the parent of <i>Object</i> as a PVOID. Callers must manually cast this return value to whatever the type of the parent of <i>Object</i> is.

## Remarks

For a graphical representation of AVStream parent/child relationships, see the diagram in <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.

The object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Minidrivers rarely use this function directly. Callers of <b>KsGetParent</b> must manually perform typecasts to and from PVOID. There are a number of inline versions that do the casting for you: <a href="..\ks\nf-ks-ksfilterfactorygetparentdevice.md">KsFilterFactoryGetParentDevice</a>, <a href="..\ks\nf-ks-ksfiltergetparentfilterfactory.md">KsFilterGetParentFilterFactory</a>, and <a href="..\ks\nf-ks-kspingetparentfilter.md">KsPinGetParentFilter</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions. |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>



<a href="..\ks\nf-ks-ksfiltergetparentfilterfactory.md">KsFilterGetParentFilterFactory</a>



<a href="..\ks\nf-ks-kspingetparentfilter.md">KsPinGetParentFilter</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



<a href="..\ks\nf-ks-ksfilterfactorygetparentdevice.md">KsFilterFactoryGetParentDevice</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetParent function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>