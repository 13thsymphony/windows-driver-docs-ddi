---
UID: NC:dispmprt.DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
title: DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION
author: windows-driver-content
description: The DxgkDdiOPMGetCOPPCompatibleInformation function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object.
old-location: display\dxgkddiopmgetcoppcompatibleinformation.htm
old-project: display
ms.assetid: 9f15df1e-bdf5-4634-97f1-78515664b594
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION, Dm_Opm_functions_7873b0b1-3983-49c4-8192-b0c59d5ae01c.xml, DxgkDdiOPMGetCOPPCompatibleInformation, DxgkDdiOPMGetCOPPCompatibleInformation callback function [Display Devices], display.dxgkddiopmgetcoppcompatibleinformation, dispmprt/DxgkDdiOPMGetCOPPCompatibleInformation
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
-	DxgkDdiOPMGetCOPPCompatibleInformation
product:
- Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback function
The<i> DxgkDdiOPMGetCOPPCompatibleInformation</i> function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object.

## Syntax

```
DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION DxgkddiOpmGetCoppCompatibleInformation;

NTSTATUS DxgkddiOpmGetCoppCompatibleInformation(
  PVOID MiniportDeviceContext,
  HANDLE ProtectedOutputHandle,
  CONST PDXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS,
  PDXGKMDT_OPM_REQUESTED_INFORMATION RequestedInformation
)
{...}
```

## Parameters

`MiniportDeviceContext`

A handle to a context block associated with a display adapter. Previously, the display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function provided this handle to the DirectX graphics kernel subsystem.

`ProtectedOutputHandle`

The handle to a protected output object. The <a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a> function creates the protected output object and returns the handle to the object. The protected output object that corresponds to this handle should have COPP semantics.

`PDXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS`



`RequestedInformation`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560910">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that receives the protected output object's COPP-compatible information if <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> returns successfully.

If <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> fails, the value that <i>RequestedInformation</i> points to is unchanged.


## Return Value

<i>DxgkDdiOPMGetCOPPCompatibleInformation</i> returns one of the following values.

This function might also return other error codes that are defined in Ntstatus.h.

## Remarks

The DirectX graphics kernel subsystem should call <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> only if the output has COPP semantics.

Before the DirectX graphics kernel subsystem passes the protected output handle to the <i>ProtectedOutputHandle</i> parameter in a call to <i>DxgkDdiOPMGetCOPPCompatibleInformation</i>, the DirectX graphics kernel subsystem always passes the protected output handle to the <a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> and <a href="https://msdn.microsoft.com/91b07a5c-ed25-4268-bd6d-273ae8b1ac28">DxgkDdiOPMGetRandomNumber</a> functions. 

Following are some facts that pertain to <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> and that do not pertain to the <a href="https://msdn.microsoft.com/3d6559e5-776e-4fc0-b99a-8818cbcc289d">DxgkDdiOPMGetInformation</a> function:

<ul>
<li>
The DirectX graphics kernel subsystem can pass a handle to a protected output only with COPP semantics. 

</li>
<li>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560859">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a> structure that the <i>Parameters</i> parameter points to is not signed.

</li>
<li>
The DirectX graphics kernel subsystem can pass the DXGKMDT_OPM_GET_ACP_AND_CGMSA_SIGNALING and DXGKMDT_OPM_GET_CONNECTED_HDCP_DEVICE_INFORMATION GUIDs in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

</li>
<li>
The DirectX graphics kernel subsystem cannot pass the DXGKMDT_OPM_GET_CURRENT_HDCP_SRM_VERSION GUID in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

</li>
<li>
The DirectX graphics kernel subsystem can specify DXGKMDT_OPM_PROTECTION_TYPE_COPP_COMPATIBLE_HDCP in the first 4 bytes of the <b>abParameters</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS along with the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS.

</li>
<li>
The DirectX graphics kernel subsystem cannot specify DXGKMDT_OPM_PROTECTION_TYPE_HDCP in the first 4 bytes of the <b>abParameters</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS along with the DXGKMDT_OPM_GET_VIRTUAL_PROTECTION_LEVEL or DXGKMDT_OPM_GET_ACTUAL_PROTECTION_LEVEL GUID in the <b>guidInformation</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS. 

</li>
</ul>
The driver must perform the following sequence when its <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> function is called.

<ol>
<li>
Verify that the protected output handle that was passed to the <i>ProtectedOutputHandle</i> parameter of <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> has COPP semantics.

</li>
<li>
Retrieve the requested information.

</li>
<li>
Copy the random number that the <b>rnRandomNumber</b> member of DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS specifies to the <b>rnRandomNumber</b> member of the DXGKMDT_OPM_STANDARD_INFORMATION, DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT, DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING, or DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION structure. The structure that is used depends on the type of information that the caller requested. The structure is set in the <b>abRequestedInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560910">DXGKMDT_OPM_REQUESTED_INFORMATION</a> structure that the <i>RequestedInformation</i> parameter points to.

</li>
<li>
Sign the DXGKMDT_OPM_REQUESTED_INFORMATION structure and place the signature in the <b>omac</b> member of DXGKMDT_OPM_REQUESTED_INFORMATION. The AES block cipher and the OMAC-1 signing algorithm should be used to sign the structure. For information about AES, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. For information about OMAC-1, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560887">DXGKMDT_OPM_OMAC</a> reference page. 

</li>
</ol>
Initially, the DirectX graphics kernel subsystem calls <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> to retrieve information about the output and then calls <a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a> one or more times to configure the output. Subsequently, the DirectX graphics kernel subsystem calls <i>DxgkDdiOPMGetCOPPCompatibleInformation</i> without also calling <i>DxgkDdiOPMConfigureProtectedOutput</i>.

<i>DxgkDdiOPMGetCOPPCompatibleInformation</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560859">DXGKMDT_OPM_COPP_COMPATIBLE_GET_INFO_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560887">DXGKMDT_OPM_OMAC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560910">DXGKMDT_OPM_REQUESTED_INFORMATION</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/a7829587-c1e7-43ec-a0bb-92bca94b7c3d">DxgkDdiOPMConfigureProtectedOutput</a>



<a href="https://msdn.microsoft.com/8143732e-cef6-49f1-9b20-db6b6ee073e6">DxgkDdiOPMCreateProtectedOutput</a>



<a href="https://msdn.microsoft.com/91b07a5c-ed25-4268-bd6d-273ae8b1ac28">DxgkDdiOPMGetRandomNumber</a>



<a href="https://msdn.microsoft.com/285521c7-4034-4db8-9441-6c4eaee27ee3">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a>