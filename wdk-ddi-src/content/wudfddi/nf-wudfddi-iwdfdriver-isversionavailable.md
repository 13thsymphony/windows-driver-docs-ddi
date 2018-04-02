---
UID: NF:wudfddi.IWDFDriver.IsVersionAvailable
title: IWDFDriver::IsVersionAvailable method
author: windows-driver-content
description: The IsVersionAvailable method determines whether the specified version of the framework is available.
old-location: wdf\iwdfdriver_isversionavailable.htm
old-project: wdf
ms.assetid: 9048a568-3369-44eb-8fa8-361ce968a253
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDriver, IWDFDriver interface, IsVersionAvailable method, IWDFDriver::IsVersionAvailable, IsVersionAvailable method, IsVersionAvailable method, IWDFDriver interface, IsVersionAvailable,IWDFDriver.IsVersionAvailable, UMDFDriverObjectRef_6ad78413-a8c5-4a9f-953d-94bd4eaf3425.xml, umdf.iwdfdriver_isversionavailable, wdf.iwdfdriver_isversionavailable, wudfddi/IWDFDriver::IsVersionAvailable
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
-	IWDFDriver.IsVersionAvailable
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFDriver::IsVersionAvailable method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsVersionAvailable</b> method determines whether the specified version of the framework is available.

## Syntax

```
BOOL IsVersionAvailable(
  UMDF_VERSION_DATA *pMinimumVersion
);
```

## Parameters

`pMinimumVersion`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561352">UMDF_VERSION_DATA</a> structure that describes the minimum version of the framework that the driver supports.


## Return Value

<b>IsVersionAvailable</b> returns a BOOL value that indicates whether the given version of the framework is available. <b>TRUE</b> indicates the version of the framework is available. <b>FALSE</b> indicates the version of the framework is not available.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561352">UMDF_VERSION_DATA</a>