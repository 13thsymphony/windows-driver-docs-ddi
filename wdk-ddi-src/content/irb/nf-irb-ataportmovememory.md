---
UID: NF:irb.AtaPortMoveMemory
title: AtaPortMoveMemory function
author: windows-driver-content
description: The AtaPortMoveMemory routine copies data from one location to another.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportmovememory.htm
old-project: storage
ms.assetid: c9d724bb-cc65-428c-ad48-21b227f3c8b1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: irb/AtaPortMoveMemory, AtaPortMoveMemory, AtaPortMoveMemory routine [Storage Devices], storage.ataportmovememory, atartns_9ecea2c5-892f-4d04-9865-30598ac4e5d6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
apiname:
-	AtaPortMoveMemory
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortMoveMemory function
The <b>AtaPortMoveMemory</b> routine copies data from one location to another.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortMoveMemory(
  _Out_ PVOID WriteBuffer,
  _In_  PVOID ReadBuffer,
  _In_  ULONG Length
);
````

## Parameters

`WriteBuffer`

A pointer to the destination buffer.

`ReadBuffer`

A pointer to the source buffer.

`Length`

Specifies the number of bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>.


## Return Value

None

## Remarks

The miniport driver calls the <b>AtaPortMoveMemory</b> routine to copy data from one system-allocated area to another. 

The location pointed to by <i>ReadBuffer</i> and <i>Length</i> can overlap the range of addresses between <i>WriteBuffer</i> and <i>Length</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |