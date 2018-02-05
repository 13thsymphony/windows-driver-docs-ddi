---
UID : NF:filterpipeline.IPrintReadStream.Seek
title : IPrintReadStream::Seek method
author : windows-driver-content
description : The Seek method changes the seek pointer to a new location in the stream.
old-location : print\iprintreadstream_seek.htm
old-project : print
ms.assetid : b563e080-32ab-47b7-94f4-1d3dd19f3311
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : Seek method [Print Devices], IPrintReadStream interface, print.iprintreadstream_seek, IPrintReadStream::Seek, filterpipeline_622c8e3a-c21f-4784-ba2d-96833fab4230.xml, Seek method [Print Devices], IPrintReadStream, IPrintReadStream interface [Print Devices], Seek method, Seek, filterpipeline/IPrintReadStream::Seek
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : filterpipeline.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : Filterpipeline.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : filterpipeline.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# Seek method
The <code>Seek</code> method changes the seek pointer to a new location in the stream.

## Syntax

````
HRESULT Seek(
  [in]  LONGLONG  dlibMove,
  [in]  DWORD     dwOrigin,
  [out] ULONGLONG *plibNewPosition
);
````

## Parameters

`dlibMove`

The displacement that is added to the location that <i>dwOrigin</i> specifies.

`dwOrigin`

The origin for the displacement that <i>dlibMove</i> specifies. The origin can be the beginning of the file (STREAM_SEEK_SET), the current seek pointer (STREAM_SEEK_CUR), or the end of the file (STREAM_SEEK_END).

`plibNewPosition`

A pointer to the location where <code>Seek</code> writes the value of the new seek pointer from the beginning of the stream.


## Return Value

<code>Seek</code> returns an <b>HRESULT</b> value.

## Remarks

The <code>Seek</code> method might block, for example, if seeking to the end of the stream.

This method is similar to the <b>IStream::Seek</b> and <b>SetFilePointerEx</b> methods. For more information about these methods, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |