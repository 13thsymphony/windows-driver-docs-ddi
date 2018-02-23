---
UID: NF:ks.KsFilterFactoryRegisterAggregatedClientUnknown
title: KsFilterFactoryRegisterAggregatedClientUnknown function
author: windows-driver-content
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\ksfilterfactoryregisteraggregatedclientunknown.htm
old-project: stream
ms.assetid: 7750a0f5-f38d-4530-81dc-589a1c2009ca
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ks/KsFilterFactoryRegisterAggregatedClientUnknown, avfunc_03ec0abd-d481-4b97-b8ab-6be504e95a55.xml, KsFilterFactoryRegisterAggregatedClientUnknown function [Streaming Media Devices], stream.ksfilterfactoryregisteraggregatedclientunknown, KsFilterFactoryRegisterAggregatedClientUnknown
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsFilterFactoryRegisterAggregatedClientUnknown
product: Windows
targetos: Windows
req.typenames: 
---


# KsFilterFactoryRegisterAggregatedClientUnknown function
This inline function is a wrapper for <a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>.

## Syntax

````
PUNKNOWN __inline KsFilterFactoryRegisterAggregatedClientUnknown(
  _In_ PKSFILTERFACTORY FilterFactory,
  _In_ PUNKNOWN         ClientUnknown
);
````

## Parameters

`FilterFactory`

A pointer to the <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> structure that represents the specified AVStream filter factory.

`ClientUnknown`

A pointer to the client <b>IUnknown</b> interface.


## Return Value

<b>KsFilterFactoryRegisterAggregatedClientUnknown</b> returns a pointer to the <b>IUnknown</b> interface of the newly created aggregate object.

## Remarks

Note that this inline function only performs a typecast and then calls <b>KsRegisterAggregatedClientUnknown</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterFactoryRegisterAggregatedClientUnknown function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>