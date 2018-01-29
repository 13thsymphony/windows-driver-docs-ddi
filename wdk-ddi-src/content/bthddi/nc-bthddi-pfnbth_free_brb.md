---
UID : NC:bthddi.PFNBTH_FREE_BRB
title : PFNBTH_FREE_BRB
author : windows-driver-content
description : The BthFreeBrb function frees a Bluetooth request block (BRB) that was allocated previously with BthAllocateBrb.
old-location : bltooth\bthfreebrb.htm
old-project : bltooth
ms.assetid : fc24cdaf-0695-4e10-82be-a7f7a916f550
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bltooth.bthfreebrb, BthFreeBrb callback function [Bluetooth Devices], BthFreeBrb, PFNBTH_FREE_BRB, PFNBTH_FREE_BRB, bthddi/BthFreeBrb, bth_funcs_434cd24f-2604-4526-ac74-14a151365658.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Desktop
req.target-min-winverclnt : Versions: Supported in Windows Vista, and later.
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# PFNBTH_FREE_BRB callback function
The 
  <i>BthFreeBrb</i> function frees a Bluetooth request block (BRB) that was allocated previously with 
  <i>BthAllocateBrb</i>.

## Syntax

```
PFNBTH_FREE_BRB PfnbthFreeBrb;

void PfnbthFreeBrb(
  __drv_freesMem(Mem)PBRB pBrb
)
{...}
```

## Parameters

`pBrb`

Pointer to the BRB to free.


## Return Value

None.

## Remarks

Profile drivers obtain a pointer to the 
    <i>BthFreeBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <mshelp:link keywords="bltooth.querying_for_bluetooth_interfaces" tabindex="0">Querying for Bluetooth
    Interfaces</mshelp:link> for more information about querying the Bluetooth driver stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |