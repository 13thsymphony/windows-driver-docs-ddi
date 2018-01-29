---
UID : NC:d3dkmthk.PDXGK_SET_SHARED_POWER_COMPONENT_STATE
title : PDXGK_SET_SHARED_POWER_COMPONENT_STATE
author : windows-driver-content
description : A callback to indicate whether the specified power component is active.
old-location : display\pdxgk_set_shared_power_component_state.htm
old-project : display
ms.assetid : 779072A4-A82B-4251-93F5-5B6C7ED0598E
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pdxgk_set_shared_power_component_state, PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback function [Display Devices], PDXGK_SET_SHARED_POWER_COMPONENT_STATE, d3dkmthk/PDXGK_SET_SHARED_POWER_COMPONENT_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dkmthk.h
req.include-header : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_TARGETMODE_DETAIL_TIMING
---


# PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback function
A callback to indicate whether the specified power component is active.

## Syntax

```
PDXGK_SET_SHARED_POWER_COMPONENT_STATE PdxgkSetSharedPowerComponentState;

NTSTATUS PdxgkSetSharedPowerComponentState(
  PVOID DeviceHandle,
  PVOID PrivateHandle,
  ULONG ComponentIndex,
  BOOLEAN Active
)
{...}
```

## Parameters

`DeviceHandle`



`PrivateHandle`



`ComponentIndex`



`Active`




## Return Value

Return STATUS_SUCCESS if the call succeeds.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |