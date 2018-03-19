---
UID: NF:ks.KsDeleteFilterFactory
title: KsDeleteFilterFactory macro
author: windows-driver-content
description: KsDeleteFilterFactory deletes a given filter factory.
old-location: stream\ksdeletefilterfactory.htm
old-project: stream
ms.assetid: 4d946524-8ad2-45a0-91be-861b30b0c297
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDeleteFilterFactory, KsDeleteFilterFactory function [Streaming Media Devices], avfunc_60aeaa09-5563-47ea-a117-4b65a468b058.xml, ks/KsDeleteFilterFactory, stream.ksdeletefilterfactory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	Ks.h
api_name:
-	KsDeleteFilterFactory
product: Windows
targetos: Windows
req.typenames: 
---


# KsDeleteFilterFactory function
<b>KsDeleteFilterFactory</b> deletes a given filter factory.

## Syntax

````
NTSTATUS KsDeleteFilterFactory(
  _In_ PKSFILTERFACTORY FilterFactory
);
````

## Parameters

`FilterFactory`

A pointer to a <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure that represents the filter factory to be deleted.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-kscreatefilterfactory.md">KsCreateFilterFactory</a>



<a href="..\ks\nf-ks-ksfilterfactoryaddcreateitem.md">KsFilterFactoryAddCreateItem</a>



<a href="..\ks\nf-ks-ksfilterfactorysetdeviceclassesstate.md">KsFilterFactorySetDeviceClassesState</a>



<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>