---
UID: NE:portcls.PC_REBALANCE_TYPE
title: PC_REBALANCE_TYPE
author: windows-driver-content
description: The PC_REBALANCE_TYPE enum describes the type of support for rebalancing.
old-location: audio\pc_rebalance_type.htm
old-project: audio
ms.assetid: CE700126-8C29-4218-9248-F722523A4DA3
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PC_REBALANCE_TYPE, PC_REBALANCE_TYPE enumeration [Audio Devices], PcRebalanceNotSupported, PcRebalanceRemoveSubdevices, audio.pc_rebalance_type, portcls/PC_REBALANCE_TYPE, portcls/PcRebalanceNotSupported, portcls/PcRebalanceRemoveSubdevices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: portcls.h
req.include-header: Portcls.h
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
-	HeaderDef
api_location:
-	portcls.h
api_name:
-	PC_REBALANCE_TYPE
product:
- Windows
targetos: Windows
req.typenames: PC_REBALANCE_TYPE
---

# PC_REBALANCE_TYPE Enumeration
The <code>PC_REBALANCE_TYPE</code> enum describes the type of support for rebalancing.

## Syntax
```
typedef enum PC_REBALANCE_TYPE {
  PcRebalanceNotSupported      ,
  PcRebalanceRemoveSubdevices
} ;
```

## Constants

<table>
            
                <tr>
                    <td>PcRebalanceNotSupported</td>
                    <td>Indicates that PcRebalance is not supported.</td>
                </tr>
            
                <tr>
                    <td>PcRebalanceRemoveSubdevices</td>
                    <td>Indicates that PcRebalance is supported via unregistering and re-registering the audio subdevices.</td>
                </tr>
</table>

## Remarks

Rebalancing is used in certain PCI scenarios. For example when additional devices are added to the PCI chain and the use of memory resources needs to be rearranged and consolidated.

For more information,  see <a href="https://msdn.microsoft.com/FCAD7F8B-AA9B-430A-BCAF-04E13FA15382">Implement PnP Rebalance for PortCls Audio Drivers</a>.

Available in Windows 10, version 1511 and later versions of Windows.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | portcls.h (include Portcls.h) |