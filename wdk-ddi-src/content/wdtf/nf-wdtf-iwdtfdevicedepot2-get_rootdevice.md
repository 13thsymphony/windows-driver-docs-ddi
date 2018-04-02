---
UID: NF:wdtf.IWDTFDeviceDepot2.get_RootDevice
title: IWDTFDeviceDepot2::get_RootDevice method
author: windows-driver-content
description: Gets the root device.
old-location: dtf\iwdtfdevicedepot2_rootdevice.htm
old-project: dtf
ms.assetid: c0d055fb-16d0-41d4-a4d7-af7505f3f7d8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDeviceDepot2, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], RootDevice property, IWDTFDeviceDepot2.RootDevice, IWDTFDeviceDepot2::get_RootDevice, Microsoft.WDTF.IWDTFDeviceDepot2.RootDevice, Microsoft::WDTF::IWDTFDeviceDepot2::RootDevice, RootDevice property [Windows Device Testing Framework], RootDevice property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, dtf.iwdtfdevicedepot2_rootdevice, get_RootDevice,IWDTFDeviceDepot2.get_RootDevice, wdtf/IWDTFDeviceDepot2::RootDevice, wdtf/IWDTFDeviceDepot2::get_RootDevice
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
-	IWDTFDeviceDepot2.RootDevice
-	IWDTFDeviceDepot2.get_RootDevice
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFDeviceDepot2::get_RootDevice method
Gets the root device.

This property is read-only.

## Syntax

```
HRESULT get_RootDevice(
  IWDTFTarget2 **pVal
);
```

## Parameters

`pVal`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406391">IWDTFDeviceDepot2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>