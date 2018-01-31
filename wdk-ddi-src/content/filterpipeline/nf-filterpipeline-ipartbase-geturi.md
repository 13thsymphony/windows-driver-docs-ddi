---
UID : NF:filterpipeline.IPartBase.GetUri
title : IPartBase::GetUri method
author : windows-driver-content
description : The GetUri method gets the URI of the part.
old-location : print\ipartbase_geturi.htm
old-project : print
ms.assetid : 5f4e3723-a30d-462d-9e7b-da05aa2e0b3c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print.ipartbase_geturi, filterpipeline/IPartBase::GetUri, IPartBase::GetUri, IPartBase, GetUri method [Print Devices], IPartBase interface, GetUri, GetUri method [Print Devices], filterpipeline_ae1b8045-4a34-4a66-939c-31363ba66c6b.xml, IPartBase interface [Print Devices], GetUri method
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


# GetUri method
The <b>GetUri</b> method gets the URI of the part.

## Syntax

````
HRESULT GetUri(
  [out] BSTR *uri
);
````

## Parameters

`uri`

The URI of the part.


## Return Value

<b>GetUri</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |