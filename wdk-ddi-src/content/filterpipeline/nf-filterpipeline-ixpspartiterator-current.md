---
UID : NF:filterpipeline.IXpsPartIterator.Current
title : IXpsPartIterator::Current method
author : windows-driver-content
description : The Current method provides the current URI and part.
old-location : print\ixpspartiterator_current.htm
old-project : print
ms.assetid : ccc8125a-c571-4267-860a-11fc313e395c
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : Current method [Print Devices], IXpsPartIterator interface, Current, Current method [Print Devices], filterpipeline_72cbd5d6-003c-410b-a943-bfd6552df8ee.xml, IXpsPartIterator, IXpsPartIterator::Current, filterpipeline/IXpsPartIterator::Current, IXpsPartIterator interface [Print Devices], Current method, print.ixpspartiterator_current
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


# Current method
The <code>Current</code> method provides the current URI and part.

## Syntax

````
HRESULT Current(
  [out] BSTR     *pUri,
  [out] IUnknown **ppXpsPart
);
````

## Parameters

`pUri`

A pointer to the URI of the part. If <b>NULL</b>, the <i>ppXpsPartparameter</i> might still be valid.

`ppXpsPart`

The current part in the iterator. If <b>NULL</b>, the <i>pUri</i> parameter might still be valid.


## Return Value

<code>Current</code> returns an <b>HRESULT</b> value.

## Remarks

Filters should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556342">IXpsPartIterator::IsDone</a> method before calling <code>Current</code>. One or both parameters can be <b>NULL</b>.

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