---
UID : NE:wdm._D3COLD_LAST_TRANSITION_STATUS
title : _D3COLD_LAST_TRANSITION_STATUS
author : windows-driver-content
description : The D3COLD_LAST_TRANSITION_STATUS enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.
old-location : kernel\d3cold_last_transition_status.htm
old-project : kernel
ms.assetid : 21E89D92-9902-4785-B022-8D17268FE75F
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : wdm/LastDStateTransitionStatusUnknown, LastDStateTransitionD3cold, D3COLD_LAST_TRANSITION_STATUS, wdm/D3COLD_LAST_TRANSITION_STATUS, LastDStateTransitionD3hot, wdm/LastDStateTransitionD3cold, _D3COLD_LAST_TRANSITION_STATUS, *PD3COLD_LAST_TRANSITION_STATUS, D3COLD_LAST_TRANSITION_STATUS enumeration [Kernel-Mode Driver Architecture], kernel.d3cold_last_transition_status, wdm/LastDStateTransitionD3hot, LastDStateTransitionStatusUnknown
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3COLD_LAST_TRANSITION_STATUS, *PD3COLD_LAST_TRANSITION_STATUS
req.product : Windows 10 or later.
---

# _D3COLD_LAST_TRANSITION_STATUS Enumeration
The <b>D3COLD_LAST_TRANSITION_STATUS</b> enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.

## Syntax
````
typedef enum _D3COLD_LAST_TRANSITION_STATUS { 
  LastDStateTransitionStatusUnknown  = 0,
  LastDStateTransitionD3hot,
  LastDStateTransitionD3cold
} D3COLD_LAST_TRANSITION_STATUS;
````

## Constants

<table>

<tr>
<td>LastDStateTransitionD3cold</td>
<td>The most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.</td>
</tr>

<tr>
<td>LastDStateTransitionD3hot</td>
<td>The most recent transition to the D3hot device power state was not followed by a transition to the D3cold device power state.</td>
</tr>

<tr>
<td>LastDStateTransitionStatusUnknown</td>
<td>Information is not available from the bus driver or platform firmware about whether the most recent transition to D3hot was followed by a transition to D3cold.</td>
</tr>
</table>

## Remarks

The <i>LastTransitionStatus</i> parameter of the <a href="..\wdm\nc-wdm-get_d3cold_last_transition_status.md">GetLastTransitionStatus</a> routine is a pointer to a variable of type <b>D3COLD_LAST_TRANSITION_STATUS</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="..\wdm\nc-wdm-get_d3cold_last_transition_status.md">GetLastTransitionStatus</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20D3COLD_LAST_TRANSITION_STATUS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>