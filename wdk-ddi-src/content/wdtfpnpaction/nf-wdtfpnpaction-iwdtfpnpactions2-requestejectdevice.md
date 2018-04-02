---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RequestEjectDevice
title: IWDTFPNPActions2::RequestEjectDevice method
author: windows-driver-content
description: Initiates a device eject.
old-location: dtf\iwdtfpnpactions2_requestejectdevice.htm
old-project: dtf
ms.assetid: 6c79b6e7-1134-4de6-b698-e09f295c3e84
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], RequestEjectDevice method, IWDTFPNPActions2::RequestEjectDevice, RequestEjectDevice method [Windows Device Testing Framework], RequestEjectDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, RequestEjectDevice,IWDTFPNPActions2.RequestEjectDevice, dtf.iwdtfpnpactions2_requestejectdevice, wdtfpnpaction/IWDTFPNPActions2::RequestEjectDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
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
-	wdtfpnpaction.h
api_name:
-	IWDTFPNPActions2.RequestEjectDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFPNPActions2::RequestEjectDevice method
Initiates a device eject.

## Syntax

```
HRESULT RequestEjectDevice(
  VARIANT_BOOL *pbSuccess
);
```

## Parameters

`pbSuccess`

True if the operation succeeds; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This will in essence call <b>CM_Request_Device_Eject()</b>. 
See the MSDN documentation for details.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdtfpnpaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451094">IWDTFPNPActions2</a>