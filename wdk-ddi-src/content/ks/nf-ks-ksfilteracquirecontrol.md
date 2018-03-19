---
UID: NF:ks.KsFilterAcquireControl
title: KsFilterAcquireControl function
author: windows-driver-content
description: The KsFilterAcquireControl function acquires the filter control mutex for the AVStream filter specified by Filter.
old-location: stream\ksfilteracquirecontrol.htm
old-project: stream
ms.assetid: 93dfe9fe-e1af-45db-ab28-fd166f511fcc
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterAcquireControl, KsFilterAcquireControl function [Streaming Media Devices], avfunc_63930ae0-491f-4916-a24f-7de5c8fa1ad3.xml, ks/KsFilterAcquireControl, stream.ksfilteracquirecontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsFilterAcquireControl
product: Windows
targetos: Windows
req.typenames: 
---


# KsFilterAcquireControl function
The<b> KsFilterAcquireControl </b>function acquires the filter control mutex for the AVStream filter specified by <i>Filter</i>.

## Syntax

````
void __inline KsFilterAcquireControl(
  _In_ PKSFILTER Filter
);
````

## Parameters

`Filter`

The <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> for which to acquire the control mutex.


## Return Value

None

## Remarks

This function is an inline call to <a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a> with the appropriate typecasting. Minidrivers that manipulate the filter control mutex should call this function instead of calling <b>KsAcquireControl </b>directly. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a>



<a href="..\ks\nf-ks-ksfilterreleasecontrol.md">KsFilterReleaseControl</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>