---
UID : NF:ks.KsCopyObjectBagItems
title : KsCopyObjectBagItems function
author : windows-driver-content
description : The KsCopyObjectBagItems function copies all items from one object bag into another.
old-location : stream\kscopyobjectbagitems.htm
old-project : stream
ms.assetid : 5b3ee4f1-5c5a-413f-b927-96293cc87e98
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsCopyObjectBagItems
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
req.alt-api : KsCopyObjectBagItems
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


# KsCopyObjectBagItems function
The<b> KsCopyObjectBagItems </b>function copies all items from one object bag into another.

## Syntax

````
NTSTATUS KsCopyObjectBagItems(
  _In_ KSOBJECT_BAG ObjectBagDestination,
  _In_ KSOBJECT_BAG ObjectBagSource
);
````

## Parameters

`ObjectBagDestination`

The KSOBJECT_BAG (equivalent to type PVOID) into which to copy items.

`ObjectBagSource`

The KSOBJECT_BAG from which items are copied to <i>ObjectBagDestination.</i>


## Return Value

Returns STATUS_SUCCESS if the copy is successful. Otherwise, it returns an error code. Most often, this is STATUS_INSUFFICIENT_RESOURCES indicating insufficient system resources to complete the copy operation. If STATUS_INSUFFICIENT_RESOURCES is returned, it is quite possible that some, but not all, of the items have been copied from <i>ObjectBagSource</i> to <i>ObjectBagDestination</i>.

## Remarks

Note that mutexes for both bags should be held. If the object bag in question is associated with a filter or a pin, acquire the filter control mutex. If the object bag belongs to a filter factory or the device, acquire the device mutex. For more information, see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a> and <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

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
<a href="..\ks\nf-ks-ksallocateobjectbag.md">KsAllocateObjectBag</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfreeobjectbag.md">KsFreeObjectBag</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksadditemtoobjectbag.md">KsAddItemToObjectBag</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksremoveitemfromobjectbag.md">KsRemoveItemFromObjectBag</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksdiscard.md">KsDiscard</a>
</dt>
<dt>
<a href="..\ks\nf-ks-_ksedit.md">_KsEdit</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspinsetpinclocktime.md">KsPinSetPinClockTime</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCopyObjectBagItems function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>