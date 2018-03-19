---
UID: NE:ucxcontroller._UCX_CONTROLLER_STATE
title: "_UCX_CONTROLLER_STATE"
author: windows-driver-content
description: This enumeration provides values to specify the UCX controller state after a reset.
old-location: buses\ucx_controller_state.htm
old-project: usbref
ms.assetid: 717BE2D2-2CF3-4A8C-B7DC-41E45C56B02B
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCX_CONTROLLER_STATE, UCX_CONTROLLER_STATE enumeration [Buses], UcxControllerStateLost, UcxControllerStatePreserved, _UCX_CONTROLLER_STATE, buses.ucx_controller_state, ucxcontroller/UCX_CONTROLLER_STATE, ucxcontroller/UcxControllerStateLost, ucxcontroller/UcxControllerStatePreserved
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucxcontroller.h
api_name:
-	UCX_CONTROLLER_STATE
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# _UCX_CONTROLLER_STATE Enumeration
This enumeration provides values to specify the UCX controller state after a  reset.

## Syntax
````
typedef enum _UCX_CONTROLLER_STATE { 
  UcxControllerStateLost,
  UcxControllerStatePreserved
} UCX_CONTROLLER_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>UcxControllerStateLost</td>
                    <td>Indicates the controller state was lost after reset.</td>
                </tr>
            
                <tr>
                    <td>UcxControllerStatePreserved</td>
                    <td>Indicates the controller state was preserved after reset.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxcontroller.h (include Ucxclass.h) |

## See Also

<a href="..\ucxcontroller\ns-ucxcontroller-_ucx_controller_reset_complete_info.md">UCX_CONTROLLER_RESET_COMPLETE_INFO</a>