---
UID : NF:ks.KsFilterGetFirstChildPin
title : KsFilterGetFirstChildPin function
author : windows-driver-content
description : The KsFilterGetFirstChildPin function returns the first instantiated pin of type PinID on the filter specified by Filter.
old-location : stream\ksfiltergetfirstchildpin.htm
old-project : stream
ms.assetid : b026908a-51d4-45a8-9c0e-1c163563bfbf
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsFilterGetFirstChildPin
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
req.alt-api : KsFilterGetFirstChildPin
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


# KsFilterGetFirstChildPin function
The<b> KsFilterGetFirstChildPin</b> function returns the first instantiated pin of type <i>PinID</i> on the filter specified by <i>Filter</i>.

## Syntax

````
PKSPIN KsFilterGetFirstChildPin(
  _In_ PKSFILTER Filter,
  _In_ ULONG     PinId
);
````

## Parameters

`Filter`

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure to query for instantiated pins.

`PinId`

The numeric ID of the pin type for which to find the first instantiated member.


## Return Value

<b>KsFilterGetFirstChildPin</b> returns a pointer to the first instantiated <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure of type <i>PinID</i> on the specified filter.

## Remarks

Note that the object hierarchy is guaranteed stable only while the appropriate mutex is held, in this case the filter control mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

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
<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergetchildpincount.md">KsFilterGetChildPinCount</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetnextsiblingpin.md">KsPinGetNextSiblingPin</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetFirstChildPin function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>