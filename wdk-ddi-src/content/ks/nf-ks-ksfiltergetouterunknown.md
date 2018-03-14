---
UID: NF:ks.KsFilterGetOuterUnknown
title: KsFilterGetOuterUnknown function
author: windows-driver-content
description: The KsFilterGetOuterUnknown function returns the outer IUnknown interface of the filter specified by Filter.
old-location: stream\ksfiltergetouterunknown.htm
old-project: stream
ms.assetid: 599a6583-dcf2-4fe3-949a-5072bff9915c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterGetOuterUnknown, KsFilterGetOuterUnknown function [Streaming Media Devices], avfunc_32947579-50ca-4942-a594-b991c42d6681.xml, ks/KsFilterGetOuterUnknown, stream.ksfiltergetouterunknown
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
-	KsFilterGetOuterUnknown
product: Windows
targetos: Windows
req.typenames: 
---


# KsFilterGetOuterUnknown function
The<b> KsFilterGetOuterUnknown </b>function returns the outer <b>IUnknown</b> interface of the filter specified by <i>Filter</i>.

## Syntax

````
PUNKNOWN __inline KsFilterGetOuterUnknown(
  _In_ PKSFILTER Filter
);
````

## Parameters

`Filter`

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to return the outer <b>IUnknown</b>.


## Return Value

<b>KsFilterGetOuterUnknown </b>returns a pointer to the outer <b>IUknown</b> interface of <i>Filter</i>. The interface can then be used to query for other interfaces, or it can be used in conjunction with a <b>Ks</b><i>Xxx</i><b>RegisterAggregatedClientUnknown</b> call to cause <i>Filter</i> to aggregate a minidriver supplied COM object.

## Remarks

This call is an inline function call to <a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-kspinregisteraggregatedclientunknown.md">KsPinRegisterAggregatedClientUnknown</a>



<a href="..\ks\nf-ks-kspingetouterunknown.md">KsPinGetOuterUnknown</a>



<a href="..\ksproxy\nn-ksproxy-ikscontrol.md">IKsControl</a>



<a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>



<b>KsRegisterAggregatedClientUnknown</b>



<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>



<a href="..\ks\nf-ks-ksfilterregisteraggregatedclientunknown.md">KsFilterRegisterAggregatedClientUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetOuterUnknown function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>