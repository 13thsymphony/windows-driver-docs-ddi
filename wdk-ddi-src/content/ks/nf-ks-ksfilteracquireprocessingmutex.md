---
UID: NF:ks.KsFilterAcquireProcessingMutex
title: KsFilterAcquireProcessingMutex function
author: windows-driver-content
description: The KsFilterAcquireProcessingMutex function acquires the processing mutex for a specified AVStream filter.
old-location: stream\ksfilteracquireprocessingmutex.htm
old-project: stream
ms.assetid: d4a2fe1a-9a16-45b8-b061-9d1b1398e801
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterAcquireProcessingMutex, KsFilterAcquireProcessingMutex function [Streaming Media Devices], avfunc_9c0c5db4-4bac-45a6-a61f-94bdcce07fd8.xml, ks/KsFilterAcquireProcessingMutex, stream.ksfilteracquireprocessingmutex
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
-	KsFilterAcquireProcessingMutex
product: Windows
targetos: Windows
req.typenames: 
---


# KsFilterAcquireProcessingMutex function
The<b> KsFilterAcquireProcessingMutex </b>function acquires the processing mutex for a specified AVStream filter.

## Syntax

````
void KsFilterAcquireProcessingMutex(
  _In_ PKSFILTER Filter
);
````

## Parameters

`Filter`

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure representing the AVStream filter for which to acquire the processing mutex.


## Return Value

None

## Remarks

AVStream holds the processing control mutex upon return from this routine. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

A minidriver that must suspend processing for a long period of time should not use this mechanism. Instead, it should manipulate the processing control gate directly by using the <b>KSGATE</b><i>Xxx</i> functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-kspinacquireprocessingmutex.md">KsPinAcquireProcessingMutex</a>



<b>KsFilterReleaseProcessingMutex</b>



<a href="..\ks\nf-ks-ksfilterattemptprocessing.md">KsFilterAttemptProcessing</a>



<a href="..\ks\nf-ks-kspingetandgate.md">KsPinGetAndGate</a>



<a href="..\ks\nf-ks-kspinreleaseprocessingmutex.md">KsPinReleaseProcessingMutex</a>