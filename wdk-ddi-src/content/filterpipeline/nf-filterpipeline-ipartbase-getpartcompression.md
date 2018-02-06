---
UID: NF:filterpipeline.IPartBase.GetPartCompression
title: IPartBase::GetPartCompression method
author: windows-driver-content
description: The GetPartCompression method gets the compression of the part.
old-location: print\ipartbase_getpartcompression.htm
old-project: print
ms.assetid: 18b2a3c2-26da-434e-bcea-89bd6ef22077
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPartBase interface [Print Devices], GetPartCompression method, IPartBase, filterpipeline/IPartBase::GetPartCompression, GetPartCompression method [Print Devices], IPartBase interface, IPartBase::GetPartCompression, filterpipeline_384bc679-c974-4c0d-86cd-32cdd0ebf7be.xml, GetPartCompression, GetPartCompression method [Print Devices], print.ipartbase_getpartcompression
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IPartBase.GetPartCompression
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# GetPartCompression method
The <b>GetPartCompression</b> method gets the compression of the part.

## Syntax

````
HRESULT GetPartCompression(
  [out] EXpsCompressionOptions *pCompression
);
````

## Parameters

`pCompression`

A pointer to the compression option data for the part.


## Return Value

<b>GetPartCompression</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |