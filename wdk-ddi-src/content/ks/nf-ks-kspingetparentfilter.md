---
UID : NF:ks.KsPinGetParentFilter
title : KsPinGetParentFilter function
author : windows-driver-content
description : The KsPinGetParentFilter function returns the parent filter of Pin.
old-location : stream\kspingetparentfilter.htm
old-project : stream
ms.assetid : adbd1e83-37f0-4e0c-92e3-92c6c79eb24f
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsPinGetParentFilter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsPinGetParentFilter
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : 
---


# KsPinGetParentFilter function
The<b> KsPinGetParentFilter</b> function returns the parent filter of <i>Pin</i>.

## Syntax

````
PKSFILTER KsPinGetParentFilter(
  _In_ PKSPIN Pin
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> for which to return the parent filter.


## Return Value

<b>KsPinGetParentFilter</b> returns a pointer to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure representing the parent filter of <i>Pin</i>.

## Remarks

<b>KsPinGetParentFilter</b> returns the filter to which <i>Pin</i> belongs. The call is an inline function call to <a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>. Note that the object hierarchy is only stable while the appropriate mutex is held, in this case the filter control mutex. See <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a> For more information about the object hierarchy in AVStream and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a> For more information about mutexes in the AVStream environment.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
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
<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgetparent.md">KsGetParent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetParentFilter function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>