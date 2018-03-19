---
UID: NF:wdtf.IWDTFLongNumbers2.get_Item
title: IWDTFLongNumbers2::get_Item method
author: windows-driver-content
description: Gets an individual device in the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_item.htm
old-project: dtf
ms.assetid: 9411437c-60d8-424e-b54c-7750f1c4dd9e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDeviceDepot2 interface [Windows Device Testing Framework], Item property, IWDTFDeviceDepot2.Item, IWDTFDeviceDepot2::get_Item, IWDTFLongNumbers2, IWDTFLongNumbers2::get_Item, Item property [Windows Device Testing Framework], Item property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, Microsoft.WDTF.IWDTFDeviceDepot2.Item, Microsoft::WDTF::IWDTFDeviceDepot2::Item, dtf.iwdtfdevicedepot2_item, get_Item,IWDTFLongNumbers2.get_Item, wdtf/IWDTFDeviceDepot2::Item, wdtf/IWDTFDeviceDepot2::get_Item
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
-	IWDTFDeviceDepot2.Item
-	IWDTFDeviceDepot2.get_Item
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_Item method
Gets an individual device in the DeviceDepot.

This property is read-only.

## Syntax

````
HRESULT get_Item(
  [in]          LONG         Index,
  [out, retval] IWDTFTarget2 **ppTarget
);
````

## Parameters

`Index`



`pNumber`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>