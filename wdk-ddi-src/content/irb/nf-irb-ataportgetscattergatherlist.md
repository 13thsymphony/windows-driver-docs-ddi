---
UID : NF:irb.AtaPortGetScatterGatherList
title : AtaPortGetScatterGatherList function
author : windows-driver-content
description : The AtaPortGetScatterGatherList routine retrieves the scatter/gather list that is associated with this request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\ataportgetscattergatherlist.htm
old-project : storage
ms.assetid : 11181574-b329-4182-8d17-93d44cb3b839
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : AtaPortGetScatterGatherList
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : irb.h
req.include-header : Ata.h, Irb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AtaPortGetScatterGatherList
req.alt-loc : ataport.lib,ataport.dll,pciidex.lib,pciidex.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ataport.lib; Pciidex.lib
req.dll : 
req.irql : 
req.typenames : IDE_POWER_STATE
---


# AtaPortGetScatterGatherList function
The <b>AtaPortGetScatterGatherList</b> routine retrieves the scatter/gather list that is associated with this request.

## Syntax

````
PIDE_SCATTER_GATHER_LIST AtaPortGetScatterGatherList(
  _In_ PVOID              ChannelExtension,
  _In_ PIDE_REQUEST_BLOCK Irb
);
````

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`Irb`

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) for which a scatter/gather list is constructed.


## Return Value

If the IRB_FLAGS_USE_DMA flag is set in the <b>IrbFlags</b> member of IRB, the <b>AtaPortGetScatterGatherList</b> routine returns a pointer to the scatter/gather list that is associated with the IRB. Otherwise, <b>AtaPortGetScatterGatherList</b> returns <b>NULL</b>.

## Remarks

Every IRB with IRB_FLAGS_USE_DMA set in the <b>IrbFlags</b> member has a scatter/gather list associated with it. 

The miniport driver must not modify the scatter/gather list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortGetScatterGatherList routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>