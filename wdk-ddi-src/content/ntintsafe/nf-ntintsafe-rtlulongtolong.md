---
UID: NF:ntintsafe.RtlULongToLong
title: RtlULongToLong function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type LONG.
old-location: kernel\rtlulongtolong.htm
old-project: kernel
ms.assetid: EA30B409-8953-488B-A8AB-84A3FBED1A20
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlULongToLong, RtlULongToLong function [Kernel-Mode Driver Architecture], kernel.rtlulongtolong, ntintsafe/RtlULongToLong
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
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlULongToLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToLong function
Converts a value of type <b>ULONG</b> to a value of type <b>LONG</b>.

## Syntax

````
NTSTATUS RtlULongToLong(
  _In_  ULONG ulOperand,
  _Out_ LONG  *plResult
);
````

## Parameters

`ulOperand`

The value to be converted.

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |