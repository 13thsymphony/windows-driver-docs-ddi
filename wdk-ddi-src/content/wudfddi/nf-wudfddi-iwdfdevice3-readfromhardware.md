---
UID: NF:wudfddi.IWDFDevice3.ReadFromHardware
title: IWDFDevice3::ReadFromHardware method
author: windows-driver-content
description: The ReadFromHardware method is used internally by the framework. Do not use.
old-location: wdf\iwdfdevice3_readfromhardware.htm
old-project: wdf
ms.assetid: 19B472D0-D607-4874-ADB9-232C379B0DFD
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDevice3, IWDFDevice3 interface, ReadFromHardware method, IWDFDevice3::ReadFromHardware, ReadFromHardware method, ReadFromHardware method, IWDFDevice3 interface, ReadFromHardware,IWDFDevice3.ReadFromHardware, umdf.iwdfdevice3_readfromhardware, wdf.iwdfdevice3_readfromhardware, wudfddi/IWDFDevice3::ReadFromHardware
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFDevice3.ReadFromHardware
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFDevice3::ReadFromHardware method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ReadFromHardware</b> method is used internally by the framework. Do not use.

## Syntax

```
SIZE_T ReadFromHardware(
  WDF_DEVICE_HWACCESS_TARGET_TYPE Type,
  WDF_DEVICE_HWACCESS_TARGET_SIZE Size,
  void                            *Address,
  void                            *Buffer,
  ULONG                           Count
);
```

## Parameters

`Type`



`Size`



`Address`



`Buffer`



`Count`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a>