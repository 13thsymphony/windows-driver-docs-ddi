---
UID: NF:hbaapi.HBA_GetPortAttributesByWWN
title: HBA_GetPortAttributesByWWN function
author: windows-driver-content
description: The HBA_GetPortAttributesByWWN routine retrieves the attributes for the port specified by the indicated port name.
old-location: storage\hba_getportattributesbywwn.htm
old-project: storage
ms.assetid: 79d63b5e-78b0-452a-aa84-695c59a7d4a5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_GetPortAttributesByWWN, HBA_GetPortAttributesByWWN routine [Storage Devices], fibreHBA_rtns_2cd8e0da-90d5-41bb-8bd9-ab2ee26ec772.xml, hbaapi/HBA_GetPortAttributesByWWN, storage.hba_getportattributesbywwn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetPortAttributesByWWN
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_GetPortAttributesByWWN function
The <b>HBA_GetPortAttributesByWWN</b> routine retrieves the attributes for the port specified by the indicated port name.

## Syntax

```
HBA_STATUS HBA_API HBA_GetPortAttributesByWWN(
  IN HBA_HANDLE          Handle,
  IN HBA_WWN             PortWWN,
  OUT HBA_PORTATTRIBUTES *PortAttributes
);
```

## Parameters

`Handle`

TBD

`PortWWN`

Contains the worldwide name (WWN) of the port whose attributes to retrieve. For a definition of worldwide names, see the T11 committee's <i>Fibre Channel HBA API </i>specification .

`PortAttributes`

TBD


## Return Value

The <b>HBA_GetPortAttributesByWWN</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.

## Remarks

The <b>HBA_GetPortAttributesByWWN</b> routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a> WMI method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557107">HBA_PortAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>