---
UID : NF:ks.KsPinGetOuterUnknown
title : KsPinGetOuterUnknown function
author : windows-driver-content
description : The KsPinGetOuterUnknown function returns the outer IUnknown of the pin specified by Pin.
old-location : stream\kspingetouterunknown.htm
old-project : stream
ms.assetid : 58b14ddd-6698-487a-925d-7d559057e55d
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsPinGetOuterUnknown
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
req.alt-api : KsPinGetOuterUnknown
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


# KsPinGetOuterUnknown function
The<b> KsPinGetOuterUnknown</b> function returns the outer <b>IUnknown</b> of the pin specified by <i>Pin</i>.

## Syntax

````
PUNKNOWN __inline KsPinGetOuterUnknown(
  _In_ PKSPIN Pin
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to return the outer <b>IUnknown</b>.


## Return Value

<b>KsPinGetOuterUnknown</b> returns a pointer to the outer <b>IUnknown</b> interface of <i>Pin</i>. This can subsequently be used to query for other interfaces.

## Remarks

<b>KsPinGetOuterUnknown</b> is an inline function call to <a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>.

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
<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nn-ks-ikscontrol.md">IKsControl</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfilterfactorygetouterunknown.md">KsFilterFactoryGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksdevicegetouterunknown.md">KsDeviceGetOuterUnknown</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetOuterUnknown function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>