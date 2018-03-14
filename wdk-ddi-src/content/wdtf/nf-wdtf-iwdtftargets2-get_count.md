---
UID: NF:wdtf.IWDTFTargets2.get_Count
title: IWDTFTargets2::get_Count method
author: windows-driver-content
description: Gets the number of devices that are currently provided by the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_count.htm
old-project: dtf
ms.assetid: 9a8c47b1-e8b9-42b4-8625-7d916178611e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Count property [Windows Device Testing Framework], Count property [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, IWDTFDeviceDepot2 interface [Windows Device Testing Framework], Count property, IWDTFDeviceDepot2.Count, IWDTFDeviceDepot2::get_Count, IWDTFTargets2, IWDTFTargets2::get_Count, Microsoft.WDTF.IWDTFDeviceDepot2.Count, Microsoft::WDTF::IWDTFDeviceDepot2::Count, dtf.iwdtfdevicedepot2_count, get_Count,IWDTFTargets2.get_Count, wdtf/IWDTFDeviceDepot2::Count, wdtf/IWDTFDeviceDepot2::get_Count
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
-	IWDTFDeviceDepot2.Count
-	IWDTFDeviceDepot2.get_Count
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# get_Count method
Gets the number of devices that are currently provided by the DeviceDepot.

This property is read-only.

## Syntax

````
HRESULT get_Count(
  [out, retval] LONG *pVal
);
````

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

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDeviceDepot2::Count property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>