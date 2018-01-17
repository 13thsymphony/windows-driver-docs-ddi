---
UID: NF:ntintsafe.RtlULongMult
title: RtlULongMult function
author: windows-driver-content
description: Multiplies one value of type ULONG by another.
old-location: kernel\rtlulongmult.htm
old-project: kernel
ms.assetid: 2D5DA884-1746-4DBC-8ABC-2D307181CCAE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongMult
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
req.alt-api: RtlULongMult
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

# RtlULongMult function



## -description
Multiplies one value of type <b>ULONG</b> by another.



## -syntax

````
NTSTATUS RtlULongMult(
  _In_  ULONG ulMultiplicand,
  _In_  ULONG ulMultiplier,
  _Out_ ULONG *pulResult
);
````


## -parameters

### -param ulMultiplicand [in]

The value to be multiplied by <i>ulMultiplier</i>.


### -param ulMultiplier [in]

The value by which to multiply <i>ulMultiplicand</i>.


### -param pulResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>