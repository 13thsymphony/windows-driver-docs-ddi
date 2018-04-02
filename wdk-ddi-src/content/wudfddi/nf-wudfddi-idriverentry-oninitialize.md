---
UID: NF:wudfddi.IDriverEntry.OnInitialize
title: IDriverEntry::OnInitialize method
author: windows-driver-content
description: The OnInitialize method performs any operations that are necessary to initialize a driver.
old-location: wdf\idriverentry_oninitialize.htm
old-project: wdf
ms.assetid: c676588e-348b-4840-9873-6b1bb2454987
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDriverEntry, IDriverEntry interface, OnInitialize method, IDriverEntry::OnInitialize, OnInitialize method, OnInitialize method, IDriverEntry interface, OnInitialize,IDriverEntry.OnInitialize, UMDFDriverObjectRef_01ebb7b4-69bb-4597-b21a-d3ff6cf3bc24.xml, umdf.idriverentry_oninitialize, wdf.idriverentry_oninitialize, wudfddi/IDriverEntry::OnInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
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
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IDriverEntry.OnInitialize
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IDriverEntry::OnInitialize method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnInitialize</b> method performs any operations that are necessary to initialize a driver.

## Syntax

```
HRESULT OnInitialize(
  IWDFDriver *pWdfDriver
);
```

## Parameters

`pWdfDriver`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface for the framework driver object that represents the driver that is loaded in the host process.


## Return Value

<b>OnInitialize</b> returns S_OK if the driver completed its global initialization. Otherwise, this method returns one of the error codes that are defined in Winerror.h. If the driver returns an error code, the framework will not load the driver.

## Remarks

The framework creates a new driver object for each driver that is loaded in the driver host process. When a driver enters the system, the framework calls <b>OnInitialize</b> to notify the driver and passes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface in the call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554885">IDriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>