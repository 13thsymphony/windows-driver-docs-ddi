---
UID: NF:storport.StorPortConvertUlongToPhysicalAddress
title: StorPortConvertUlongToPhysicalAddress function
author: windows-driver-content
description: The StorPortConvertUlongToPhysicalAddress routine converts an unsigned long address into a physical address.
old-location: storage\storportconvertulongtophysicaladdress.htm
old-project: storage
ms.assetid: 772ca60b-a957-47de-b95d-486497b295ce
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortConvertUlongToPhysicalAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortConvertUlongToPhysicalAddress
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortConvertUlongToPhysicalAddress function



## -description
The <b>StorPortConvertUlongToPhysicalAddress</b> routine converts an unsigned long address into a physical address.



## -syntax

````
STORPORT_API STOR_PHYSICAL_ADDRESS StorPortConvertUlongToPhysicalAddress(
  _In_ ULONG_PTR UlongAddress
);
````


## -parameters

### -param UlongAddress [in]

Contains the address to be converted.


## -returns
The <b>StorPortConvertUlongToPhysicalAddress</b> routine returns the physical address that corresponds to the unsigned long address that the caller passed in.

<b>ULONG64</b>

<b>StorPortConvertPhysicalAddressToULong64</b> returns a ULONG64 value derived from the physical address that was passed to it.

 

StorPortConvertPhysicalAddressToULong64 uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

<b>ULONG64</b>

<b>StorPortConvertPhysicalAddressToULong64</b> returns a ULONG64 value derived from the physical address that was passed to it.

 

StorPortConvertPhysicalAddressToULong64 uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.


## -remarks
<b>StorPortConvertUlongToPhysicalAddress</b> uses <b>STOR_PHYSICAL_ADDRESS</b> to represent physical addresses.

The <b>STOR_PHYSICAL_ADDRESS</b> type is an operating system-independent data type that Storport miniport drivers use to represent either a physical addresses or a bus-relative address. 

The StorPortConvertPhysicalAddressToULong64 macro converts a physical address to a ULONG64 value.



<a id="Address__in_"></a><a id="address__in_"></a><a id="ADDRESS__IN_"></a><i>Address [in]</i>

<b>STOR_PHYSICAL_ADDRESS</b>

Specifies an address value of type STOR_PHYSICAL_ADDRESS.

<a id="Return_value"></a><a id="return_value"></a><a id="RETURN_VALUE"></a>Return value</p>