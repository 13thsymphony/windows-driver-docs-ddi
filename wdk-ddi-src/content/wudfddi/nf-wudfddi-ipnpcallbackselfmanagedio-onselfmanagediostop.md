---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoStop
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoStop method
author: windows-driver-content
description: The OnSelfManagedIoStop method is not used in the current version of the UMDF.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagediostop.htm
old-project: wdf
ms.assetid: 490c95f5-ea93-4521-8fa5-4ca1f83ff19d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPnpCallbackSelfManagedIo, IPnpCallbackSelfManagedIo interface, OnSelfManagedIoStop method, IPnpCallbackSelfManagedIo::OnSelfManagedIoStop, OnSelfManagedIoStop method, OnSelfManagedIoStop method, IPnpCallbackSelfManagedIo interface, OnSelfManagedIoStop,IPnpCallbackSelfManagedIo.OnSelfManagedIoStop, UMDFDeviceObjectRef_d9eba21f-f9a7-48d2-a8e7-f71a735246bc.xml, umdf.ipnpcallbackselfmanagedio_onselfmanagediostop, wdf.ipnpcallbackselfmanagedio_onselfmanagediostop, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoStop
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
-	IPnpCallbackSelfManagedIo.OnSelfManagedIoStop
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# OnSelfManagedIoStop method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoStop</b> method is not used in the current version of the UMDF.

## Syntax

````
HRESULT OnSelfManagedIoStop(
  [in] IWDFDevice *pWdfDevice
);
````

## Parameters

`pWdfDevice`




## Return Value

This method is not currently used.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |