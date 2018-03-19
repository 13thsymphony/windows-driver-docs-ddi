---
UID: NF:ks.KsStreamPointerAdvanceOffsetsAndUnlock
title: KsStreamPointerAdvanceOffsetsAndUnlock function
author: windows-driver-content
description: The KsStreamPointerAdvanceOffsetsAndUnlock function advances StreamPointer the specified number of bytes into the stream (adjusting the OffsetIn and OffsetOut fields of StreamPointer as requested) and unlocks it.
old-location: stream\ksstreampointeradvanceoffsetsandunlock.htm
old-project: stream
ms.assetid: bb15eb8e-b609-4110-b0de-71efb8ef1f5e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsStreamPointerAdvanceOffsetsAndUnlock, KsStreamPointerAdvanceOffsetsAndUnlock function [Streaming Media Devices], avfunc_5f1d19bb-e367-4df3-9423-0263bda1cd54.xml, ks/KsStreamPointerAdvanceOffsetsAndUnlock, stream.ksstreampointeradvanceoffsetsandunlock
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsStreamPointerAdvanceOffsetsAndUnlock
product: Windows
targetos: Windows
req.typenames: 
---


# KsStreamPointerAdvanceOffsetsAndUnlock function
The<b> KsStreamPointerAdvanceOffsetsAndUnlock</b> function advances <i>StreamPointer</i> the specified number of bytes into the stream (adjusting the <i>OffsetIn </i>and <i>OffsetOut </i>fields of <i>StreamPointer</i> as requested) and unlocks it.

## Syntax

````
void KsStreamPointerAdvanceOffsetsAndUnlock(
  _In_ PKSSTREAM_POINTER StreamPointer,
  _In_ ULONG             InUsed,
  _In_ ULONG             OutUsed,
  _In_ BOOLEAN           Eject
);
````

## Parameters

`StreamPointer`

A pointer to a <a href="..\ks\ns-ks-_ksstream_pointer.md">KSSTREAM_POINTER</a> structure representing the stream pointer to advance and unlock.

`InUsed`

This parameter contains the number of input bytes used. AVStream advances the input offset by this number of bytes. This must be less than the total number of remaining unused bytes in the frame referenced by <i>StreamPointer</i>. If <i>InUsed</i> is equal to the remaining number of bytes in the frame referenced by <i>StreamPointer</i>, AVStream advances <i>StreamPointer </i>to the next available data frame.

`OutUsed`

This parameter contains the number of output bytes used. AVStream advances the output offset by this number of bytes. This must be less than the total number of remaining unused bytes in the frame referenced by <i>StreamPointer</i>. If <i>OutUsed</i> is equal to the remaining number of bytes in the frame referenced by <i>StreamPointer</i>, AVStream advances <i>StreamPointer </i>to the next available data frame.

`Eject`

This parameter indicates whether <i>StreamPointer</i> should be advanced. If this parameter is set to <b>TRUE</b>, AVStream advances the stream pointer to the next available data frame regardless of the values in <i>InUsed </i>and <i>OutUsed</i>.


## Return Value

None

## Remarks

If using the specified number of bytes in the stream pointer results in zero remaining bytes to process in the current frame, AVStream advances the stream pointer to the next available frame. Minidrivers can force advancement to the next frame regardless of the number of bytes used by setting <i>Eject</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ks\nf-ks-ksstreampointerlock.md">KsStreamPointerLock</a>



<a href="..\ks\nf-ks-ksstreampointerdelete.md">KsStreamPointerDelete</a>



<a href="..\ks\nf-ks-ksstreampointeradvance.md">KsStreamPointerAdvance</a>



<a href="..\ks\nf-ks-ksstreampointerclone.md">KsStreamPointerClone</a>



<a href="..\ks\nf-ks-ksstreampointerunlock.md">KsStreamPointerUnlock</a>