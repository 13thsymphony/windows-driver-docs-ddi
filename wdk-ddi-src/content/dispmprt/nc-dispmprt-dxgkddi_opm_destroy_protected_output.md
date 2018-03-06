---
UID: NC:dispmprt.DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT
title: DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT
author: windows-driver-content
description: The DxgkDdiOPMDestroyProtectedOutput function destroys the given protected output object.
old-location: display\dxgkddiopmdestroyprotectedoutput.htm
old-project: display
ms.assetid: a03381ba-342e-409f-99ab-9790e1d74371
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT, Dm_Opm_functions_e744a9ff-d14b-4cef-aed6-4dba714dc695.xml, DxgkDdiOPMDestroyProtectedOutput, DxgkDdiOPMDestroyProtectedOutput callback function [Display Devices], display.dxgkddiopmdestroyprotectedoutput, dispmprt/DxgkDdiOPMDestroyProtectedOutput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiOPMDestroyProtectedOutput
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT callback function
The <i>DxgkDdiOPMDestroyProtectedOutput</i> function destroys the given protected output object.

## Syntax

```
DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT DxgkddiOpmDestroyProtectedOutput;

NTSTATUS DxgkddiOpmDestroyProtectedOutput(
  PVOID MiniportDeviceContext,
  HANDLE ProtectedOutputHandle
)
{...}
```

## Parameters

`MiniportDeviceContext`

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.

`ProtectedOutputHandle`

The handle to a protected output object. The <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object.


## Return Value

<i>DxgkDdiOPMDestroyProtectedOutput</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes that are defined in <i>Ntstatus.h</i>. 

<div class="alert"><b>Note</b>  <i>DxgkDdiOPMDestroyProtectedOutput</i> cannot fail if the ProtectedOutputHandle parameter contains a valid protected output handle. </div>
<div> </div>

## Remarks

The DirectX graphics kernel subsystem calls <i>DxgkDdiOPMDestroyProtectedOutput</i> when it finishes using the protected output object.

<i>DxgkDdiOPMDestroyProtectedOutput</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_create_protected_output.md">DxgkDdiOPMCreateProtectedOutput</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>