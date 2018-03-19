---
UID: NF:wudfddi.IWDFDevice.GetDriver
title: IWDFDevice::GetDriver method
author: windows-driver-content
description: The GetDriver method retrieves the interface to the parent driver object of a device instance.
old-location: wdf\iwdfdevice_getdriver.htm
old-project: wdf
ms.assetid: 5d17d970-56b7-494a-aa7b-d60065ff06d8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetDriver method, GetDriver method, IWDFDevice interface, GetDriver,IWDFDevice.GetDriver, IWDFDevice, IWDFDevice interface, GetDriver method, IWDFDevice::GetDriver, UMDFDeviceObjectRef_6c0cfbb6-1ee7-4c7b-b4ec-0b957630e094.xml, umdf.iwdfdevice_getdriver, wdf.iwdfdevice_getdriver, wudfddi/IWDFDevice::GetDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice.GetDriver
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetDriver method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDriver</b> method retrieves the interface to the parent driver object of a device instance.

## Syntax

````
void GetDriver(
  [out] IWDFDriver **ppWdfDriver
);
````

## Parameters

`ppWdfDriver`

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface for the parent driver object.


## Return Value

None

## Remarks

For a code example of how to use the GetDriver method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>