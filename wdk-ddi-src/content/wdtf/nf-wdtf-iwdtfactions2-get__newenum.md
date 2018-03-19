---
UID: NF:wdtf.IWDTFActions2.get__NewEnum
title: IWDTFActions2::get__NewEnum method
author: windows-driver-content
description: Gets a new iteration variable that the For Each loop structure implicitly uses.
old-location: dtf\iwdtfdevicedepot2__newenum.htm
old-project: dtf
ms.assetid: cc864595-a0bb-4fd4-9d93-830e8fd6a346
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFActions2, IWDTFActions2::get__NewEnum, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], _NewEnum property, IWDTFDeviceDepot2._NewEnum, IWDTFDeviceDepot2::get__NewEnum, Microsoft.WDTF.IWDTFDeviceDepot2._NewEnum, Microsoft::WDTF::IWDTFDeviceDepot2::_NewEnum, _NewEnum property [Windows Device Testing Framework], _NewEnum property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, dtf.iwdtfdevicedepot2__newenum, get__NewEnum,IWDTFActions2.get__NewEnum, wdtf/IWDTFDeviceDepot2::_NewEnum, wdtf/IWDTFDeviceDepot2::get__NewEnum
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFDeviceDepot2._NewEnum
-	IWDTFDeviceDepot2.get__NewEnum
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get__NewEnum method
Gets a new iteration variable that the <b>For Each</b> 
loop structure implicitly uses.

This property is read-only.

## Syntax

````
HRESULT get__NewEnum(
  [out, retval] IUnknown **ppNewEnum
);
````

## Parameters

`ppNewEnum`




## Return Value

None

## Remarks

You cannot access the <b>_NewEnum</b> property from the 
JScript programming language.

You must use the Active Template Library (ATL) to implement this functionality. 
For more information about how ATL implements this functionality, see the 
<b>ICollectionOnSTLImpl </b>interface in the MSDN Library.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>