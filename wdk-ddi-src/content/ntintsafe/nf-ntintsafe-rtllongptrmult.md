---
UID: NF:ntintsafe.RtlLongPtrMult
title: RtlLongPtrMult function
author: windows-driver-content
description: Multiplies one value of type LONG_PTR by another.
old-location: kernel\rtllongptrmult.htm
old-project: kernel
ms.assetid: AF602DBE-E106-4105-B56B-DE9EE7691A05
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongPtrMult
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlLongPtrMult
req.alt-loc: Ntintsafe.h
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
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongPtrMult function



## -description
Multiplies one value of type <b>LONG_PTR</b> by another.



## -syntax

````
NTSTATUS RtlLongPtrMult(
  _In_  LONG_PTR lMultiplicand,
  _In_  LONG_PTR lMultiplier,
  _Out_ LONG_PTR *plResult
);
````


## -parameters

### -param lMultiplicand [in]

The value to be multiplied by <i>lMultiplier</i>.


### -param lMultiplier [in]

The value by which to multiply <i>lMultiplicand</i>.


### -param plResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>