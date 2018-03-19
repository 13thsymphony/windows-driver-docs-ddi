---
UID: NF:ksproxy.IKsPin.KsQueryMediums
title: IKsPin::KsQueryMediums method
author: windows-driver-content
description: The KsQueryMediums method retrieves mediums that a pin supports.
old-location: stream\ikspin_ksquerymediums.htm
old-project: stream
ms.assetid: de6efd10-7f97-422a-abd4-c21c4cbc1dd7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPin, IKsPin interface [Streaming Media Devices], KsQueryMediums method, IKsPin::KsQueryMediums, KsQueryMediums method [Streaming Media Devices], KsQueryMediums method [Streaming Media Devices], IKsPin interface, KsQueryMediums,IKsPin.KsQueryMediums, ksproxy/IKsPin::KsQueryMediums, ksproxy_88debe31-2dd5-41bc-80c0-164b28dc586f.xml, stream.ikspin_ksquerymediums
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsPin.KsQueryMediums
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsQueryMediums method
The <b>KsQueryMediums</b> method retrieves mediums that a pin supports.

## Syntax

````
HRESULT KsQueryMediums(
  [out] PKSMULTIPLE_ITEM *MediumList
);
````

## Parameters

`MediumList`

Pointer to a buffer that receives a pointer to a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure, followed by a sequence of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a> structures that describe medium types. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The returned mediums are ordered by preference. 

Applications call <b>KsQueryMediums</b> to retrieve mediums that pins support in order to build a filter graph.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563538">KSPIN_MEDIUM</a>