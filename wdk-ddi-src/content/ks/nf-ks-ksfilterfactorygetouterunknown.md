---
UID: NF:ks.KsFilterFactoryGetOuterUnknown
title: KsFilterFactoryGetOuterUnknown function
author: windows-driver-content
description: The KsFilterFactoryGetOuterUnknown function returns the outer IUnknown of the specified filter factory.
old-location: stream\ksfilterfactorygetouterunknown.htm
old-project: stream
ms.assetid: 65244091-6089-4d0c-abf4-1178cf0bf1b5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterFactoryGetOuterUnknown, KsFilterFactoryGetOuterUnknown function [Streaming Media Devices], avfunc_4a154d39-a344-4f58-8abe-cbf2a0926271.xml, ks/KsFilterFactoryGetOuterUnknown, stream.ksfilterfactorygetouterunknown
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
-	KsFilterFactoryGetOuterUnknown
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsFilterFactoryGetOuterUnknown function
The<b> KsFilterFactoryGetOuterUnknown </b>function returns the outer <b>IUnknown</b> of the specified filter factory.

## Syntax

```
PUNKNOWN KsFilterFactoryGetOuterUnknown(
  PKSFILTERFACTORY FilterFactory
);
```

## Parameters

`FilterFactory`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> for which to return the outer unknown interface.


## Return Value

<b>KsFilterFactoryGetOuterUnknown </b>returns the outer <b>IUnknown</b> of <i>FilterFactory</i>. The minidriver can then use it to query for other interfaces.

## Remarks

This call is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562655">KsGetOuterUnknown</a>.

For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559766">IKsControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562547">KsFilterGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562549">KsFilterRegisterAggregatedClientUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562655">KsGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563515">KsPinGetOuterUnknown</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>