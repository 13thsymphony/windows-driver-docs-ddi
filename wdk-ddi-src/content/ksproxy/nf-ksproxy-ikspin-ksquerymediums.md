---
UID : NF:ksproxy.IKsPin.KsQueryMediums
title : IKsPin::KsQueryMediums method
author : windows-driver-content
description : The KsQueryMediums method retrieves mediums that a pin supports.
old-location : stream\ikspin_ksquerymediums.htm
old-project : stream
ms.assetid : de6efd10-7f97-422a-abd4-c21c4cbc1dd7
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IKsPin::KsQueryMediums, KsQueryMediums method [Streaming Media Devices], stream.ikspin_ksquerymediums, IKsPin interface [Streaming Media Devices], KsQueryMediums method, KsQueryMediums method [Streaming Media Devices], IKsPin interface, ksproxy_88debe31-2dd5-41bc-80c0-164b28dc586f.xml, IKsPin, ksproxy/IKsPin::KsQueryMediums, KsQueryMediums
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
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
req.lib : ksproxy.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PIPE_STATE
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

Pointer to a buffer that receives a pointer to a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> structure, followed by a sequence of <a href="..\ks\ns-ks-ksidentifier.md">KSPIN_MEDIUM</a> structures that describe medium types. The KSMULTIPLE_ITEM structure is a header that describes the size of the buffer and the number of entries in the list that follows the header.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The returned mediums are ordered by preference. 

Applications call <b>KsQueryMediums</b> to retrieve mediums that pins support in order to build a filter graph.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a>

<a href="..\ks\ns-ks-ksidentifier.md">KSPIN_MEDIUM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPin::KsQueryMediums method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>