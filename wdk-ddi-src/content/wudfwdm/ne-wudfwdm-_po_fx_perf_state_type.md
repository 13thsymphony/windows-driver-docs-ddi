---
UID: NE:wudfwdm._PO_FX_PERF_STATE_TYPE
title: "_PO_FX_PERF_STATE_TYPE"
author: windows-driver-content
description: The PO_FX_PERF_STATE_TYPE enumeration contains values that describe the type of performance states in a PO_FX_COMPONENT_PERF_SET.
old-location: kernel\po_fx_perf_state_type.htm
old-project: kernel
ms.assetid: E3BFBF03-8130-4EFF-95F4-030107AF4D75
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_PO_FX_PERF_STATE_TYPE, wdm/PPO_FX_PERF_STATE_TYPE, kernel.po_fx_perf_state_type, wdm/PoFxPerfStateTypeMaximum, PPO_FX_PERF_STATE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], wdm/PoFxPerfStateTypeRange, PPO_FX_PERF_STATE_TYPE, PO_FX_PERF_STATE_TYPE, PoFxPerfStateTypeMaximum, PoFxPerfStateTypeDiscrete, *PPO_FX_PERF_STATE_TYPE, wdm/PO_FX_PERF_STATE_TYPE, PO_FX_PERF_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PoFxPerfStateTypeRange, wdm/PoFxPerfStateTypeDiscrete"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfwdm.h
req.include-header: Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	PO_FX_PERF_STATE_TYPE
product: Windows
targetos: Windows
req.typenames: "*PPO_FX_PERF_STATE_TYPE, PO_FX_PERF_STATE_TYPE"
req.product: Windows 10 or later.
---

# _PO_FX_PERF_STATE_TYPE Enumeration
The <b>PO_FX_PERF_STATE_TYPE</b> enumeration contains values that describe the type of performance states in a <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a>.

## Syntax
````
typedef enum _PO_FX_PERF_STATE_TYPE { 
  PoFxPerfStateTypeDiscrete,
  PoFxPerfStateTypeRange,
  PoFxPerfStateTypeMaximum
} PO_FX_PERF_STATE_TYPE, *PPO_FX_PERF_STATE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PoFxPerfStateTypeDiscrete</td>
                    <td>Indicates that the performance state set contains a discrete number of states.</td>
                </tr>
            
                <tr>
                    <td>PoFxPerfStateTypeMaximum</td>
                    <td>This value is reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>PoFxPerfStateTypeRange</td>
                    <td>Indicates that the performance state set contains a continuous distribution of  states between a minimum and maximum value.</td>
                </tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> structure is a value from the <b>PO_FX_PERF_STATE_TYPE</b> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | wudfwdm.h (include Wudfwdm.h) |

## See Also

<a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_PERF_STATE_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>