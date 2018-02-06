---
UID: NF:filterpipeline.IXpsPartIterator.IsDone
title: IXpsPartIterator::IsDone method
author: windows-driver-content
description: The IsDone method determines whether the iterator has finished the iteration.
old-location: print\ixpspartiterator_isdone.htm
old-project: print
ms.assetid: 80877e8e-378f-4849-a8ce-b0651fdc2755
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IsDone, IXpsPartIterator, print.ixpspartiterator_isdone, IXpsPartIterator::IsDone, IXpsPartIterator interface [Print Devices], IsDone method, IsDone method [Print Devices], filterpipeline_c3b7b22e-6a29-463a-a516-d7857413050e.xml, IsDone method [Print Devices], IXpsPartIterator interface, filterpipeline/IXpsPartIterator::IsDone
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
-	Filterpipeline.h
apiname:
-	IXpsPartIterator.IsDone
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# IsDone method
The <code>IsDone</code> method determines whether the iterator has finished  the iteration.

## Syntax

````
BOOL STDMETHODCALLTYPE IsDone(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

<code>IsDone</code> returns <b>true</b> if the iterator has finished iterating.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |