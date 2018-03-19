---
UID: NF:ks.KsGetNextSibling
title: KsGetNextSibling function
author: windows-driver-content
description: The KsGetNextSibling function returns the next sibling of a given object.
old-location: stream\ksgetnextsibling.htm
old-project: stream
ms.assetid: 509cf778-2b0c-4dd2-982d-0c7be95ad407
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetNextSibling, KsGetNextSibling function [Streaming Media Devices], avfunc_0fedfc95-34c0-44d9-bed4-fff6bf6bd467.xml, ks/KsGetNextSibling, stream.ksgetnextsibling
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
-	KsGetNextSibling
product: Windows
targetos: Windows
req.typenames: 
---


# KsGetNextSibling function
The<b> KsGetNextSibling </b>function returns the next sibling of a given object.

## Syntax

````
PVOID KsGetNextSibling(
  _In_ PVOID Object
);
````

## Parameters

`Object`

The object for which to find the next sibling.


## Return Value

<b>KsGetNextSibling</b> returns the next sibling object of <i>Object</i>. If no such sibling object exists, it returns <b>NULL</b>.

## Remarks

If <i>Object</i> is a filter factory, <b>KsGetNextSibling </b>returns the next filter factory belonging to the parent device, and so on. Callers must perform appropriate typecasting to and from PVOID.

The object hierarchy is guaranteed stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a> and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Minidrivers rarely call <b>KsGetNextSibling</b> directly. There are a number of functions that are inline calls to <b>KsGetNextSibling</b> and that perform the typecasting for you: <a href="..\ks\nf-ks-ksfilterfactorygetnextsiblingfilterfactory.md">KsFilterFactoryGetNextSiblingFilterFactory</a>, <a href="..\ks\nf-ks-ksfiltergetnextsiblingfilter.md">KsFilterGetNextSiblingFilter</a>, and <a href="..\ks\nf-ks-kspingetnextsiblingpin.md">KsPinGetNextSiblingPin</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-ksfiltergetnextsiblingfilter.md">KsFilterGetNextSiblingFilter</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>



<a href="..\ks\nf-ks-ksfilterfactorygetnextsiblingfilterfactory.md">KsFilterFactoryGetNextSiblingFilterFactory</a>



<a href="..\ks\nf-ks-kspingetnextsiblingpin.md">KsPinGetNextSiblingPin</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>