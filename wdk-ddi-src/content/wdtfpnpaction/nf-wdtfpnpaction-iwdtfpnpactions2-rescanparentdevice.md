---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.RescanParentDevice
title: IWDTFPNPActions2::RescanParentDevice method
author: windows-driver-content
description: Rescans and re-enumerates the target device's parent device.
old-location: dtf\iwdtfpnpactions2_rescanparentdevice.htm
old-project: dtf
ms.assetid: 10365869-3512-41cc-95eb-7b8658bffd9b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFPNPActions2, IWDTFPNPActions2 interface [Windows Device Testing Framework], RescanParentDevice method, IWDTFPNPActions2::RescanParentDevice, RescanParentDevice method [Windows Device Testing Framework], RescanParentDevice method [Windows Device Testing Framework], IWDTFPNPActions2 interface, RescanParentDevice,IWDTFPNPActions2.RescanParentDevice, dtf.iwdtfpnpactions2_rescanparentdevice, wdtfpnpaction/IWDTFPNPActions2::RescanParentDevice
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
-	IWDTFPNPActions2.RescanParentDevice
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFPNPActions2::RescanParentDevice method
Rescans and re-enumerates the target device's parent device.

## Syntax

```
HRESULT RescanParentDevice(
  VARIANT_BOOL *pbSuccess
);
```

## Parameters

`pbSuccess`

True if the operation succeeds; otherwise, false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

In essence, <b>RescanParentDevice</b> calls 
<b>CM_Reenumerate_DevNode()</b>. See the MSDN documentation for 
<b>CM_Reenumerate_DevNode()</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdtfpnpaction.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451094">IWDTFPNPActions2</a>