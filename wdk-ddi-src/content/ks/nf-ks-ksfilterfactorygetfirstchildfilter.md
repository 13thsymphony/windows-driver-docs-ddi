---
UID : NF:ks.KsFilterFactoryGetFirstChildFilter
title : KsFilterFactoryGetFirstChildFilter function
author : windows-driver-content
description : The KsFilterFactoryGetFirstChildFilter function returns the first instantiated filter created by FilterFactory.
old-location : stream\ksfilterfactorygetfirstchildfilter.htm
old-project : stream
ms.assetid : 72eb23aa-4f0e-4ef5-baee-c0735253684e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsFilterFactoryGetFirstChildFilter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsFilterFactoryGetFirstChildFilter
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : 
---


# KsFilterFactoryGetFirstChildFilter function
The<b> KsFilterFactoryGetFirstChildFilter</b> function returns the first instantiated filter created by <i>FilterFactory</i>.

## Syntax

````
PKSFILTER __inline KsFilterFactoryGetFirstChildFilter(
  _In_ PKSFILTERFACTORY FilterFactory
);
````

## Parameters

`FilterFactory`

A pointer to the <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure for which to find the first instantiated child filter.


## Return Value

<b>KsFilterFactoryGetFirstChildFilter</b> returns a pointer to the first instantiated <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure created by <i>FilterFactory</i>. If there are no instantiated filters created by <i>FilterFactory</i>, <b>NULL</b> is returned.

## Remarks

This call is an inline function call to <a href="..\ks\nf-ks-ksgetfirstchild.md">KsGetFirstChild</a>. Note that the object hierarchy is guaranteed to be stable only while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgetfirstchild.md">KsGetFirstChild</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergetnextsiblingfilter.md">KsFilterGetNextSiblingFilter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryGetFirstChildFilter function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>