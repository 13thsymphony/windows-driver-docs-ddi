---
UID : NC:irb.IDE_HW_RESET
title : IDE_HW_RESET
author : windows-driver-content
description : The IdeHwReset miniport driver routine resets the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\idehwreset.htm
old-project : storage
ms.assetid : 722810c8-ddf2-4910-8cf3-af3511d8c167
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.idehwreset, IdeHwReset routine [Storage Devices], IdeHwReset, IDE_HW_RESET, IDE_HW_RESET, irb/IdeHwReset, atartns_c3c999ac-3737-48ab-be9b-99c83013b878.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : irb.h
req.include-header : Irb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : LUID
---


# IDE_HW_RESET callback function
The <b><i>IdeHwReset</i></b> miniport driver routine resets the channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
IDE_HW_RESET IdeHwReset;

BOOLEAN IdeHwReset(
  PVOID ChannelExtension
)
{...}
```

## Parameters

`ChannelExtension`

A pointer to the channel extension.


## Return Value

<b><i>IdeHwReset</i></b> returns <b>TRUE</b> if the reset operation succeeded.  Otherwise, it returns <b>FALSE</b>.

## Remarks

The <b><i>IdeHwReset</i></b> routine should complete all pending requests and reset the indicated channel.

<b><i>IdeHwReset</i></b> can be called even if the miniport driver is not ready for another request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Irb.h) |