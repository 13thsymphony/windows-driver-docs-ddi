---
UID: NE:d3dkmdt._DXGKMDT_OPM_STATUS
title: "_DXGKMDT_OPM_STATUS"
author: windows-driver-content
description: The DXGKMDT_OPM_STATUS enumeration identifies the status of a protected output.
old-location: display\dxgkmdt_opm_status.htm
old-project: display
ms.assetid: e3bfde85-e8a0-41df-9248-f48ceb8b5304
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKMDT_OPM_STATUS_LINK_LOST, DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED, d3dkmdt/DXGKMDT_OPM_STATUS_LINK_LOST, DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED, d3dkmdt/DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED, d3dkmdt/DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED, DXGKMDT_OPM_STATUS enumeration [Display Devices], d3dkmdt/DXGKMDT_OPM_STATUS_TAMPERING_DETECTED, DXGKMDT_OPM_STATUS_TAMPERING_DETECTED, DmEnums_77faebe8-d3a4-461f-9f03-daa2d81da828.xml, d3dkmdt/DXGKMDT_OPM_STATUS_NORMAL, d3dkmdt/DXGKMDT_OPM_STATUS, DXGKMDT_OPM_STATUS, _DXGKMDT_OPM_STATUS, DXGKMDT_OPM_STATUS_NORMAL, display.dxgkmdt_opm_status
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	DXGKMDT_OPM_STATUS
product: Windows
targetos: Windows
req.typenames: DXGKMDT_OPM_STATUS
---

# _DXGKMDT_OPM_STATUS Enumeration
The DXGKMDT_OPM_STATUS enumeration identifies the status of a protected output.

## Syntax
````
typedef enum _DXGKMDT_OPM_STATUS { 
  DXGKMDT_OPM_STATUS_NORMAL                        = 0x00,
  DXGKMDT_OPM_STATUS_LINK_LOST                     = 0x01,
  DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED        = 0x02,
  DXGKMDT_OPM_STATUS_TAMPERING_DETECTED            = 0x04,
  DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED  = 0x08
} DXGKMDT_OPM_STATUS;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_OPM_STATUS_LINK_LOST</td>
                    <td>Indicates that although the protected output detected no tampering, an output protection technology unexpectedly stopped working. 

This status bit must be set if DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED is also set.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_STATUS_NORMAL</td>
                    <td>Indicates that the protected output is working correctly.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_STATUS_RENEGOTIATION_REQUIRED</td>
                    <td>Indicates that the end user caused the configuration of the physical connector to change. Therefore, a renegotiation is required.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_STATUS_REVOKED_HDCP_DEVICE_ATTACHED</td>
                    <td>Indicates that a revoked High-bandwidth Digital Content Protection (HDCP) device is directly or indirectly attached to a protected output. If HDCP is not enabled, the protected output is not required to detect revoked devices. If HDCP is enabled, the protected output must detect revoked devices. The driver sets this status value only from a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> function to determine if HDCP is enabled.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_STATUS_TAMPERING_DETECTED</td>
                    <td>Indicates that tampering with the graphics adapter or the adapter's display miniport driver has occurred.</td>
                </tr>
</table>

    ## Remarks

        The display miniport driver returns status about a protected output whenever the driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a> functions are called to retrieve information about the protected output. For more information about returning a protected output's status, see <a href="https://msdn.microsoft.com/9945ae9c-1c11-4266-8a5c-d0ffe5ba4b5f">Reporting Status about a Protected Output</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md">DxgkDdiOPMGetCOPPCompatibleInformation</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_acp_and_cgmsa_signaling.md">DXGKMDT_OPM_ACP_AND_CGMSA_SIGNALING</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_actual_output_format.md">DXGKMDT_OPM_ACTUAL_OUTPUT_FORMAT</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_connected_hdcp_device_information.md">DXGKMDT_OPM_CONNECTED_HDCP_DEVICE_INFORMATION</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_standard_information.md">DXGKMDT_OPM_STANDARD_INFORMATION</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_information.md">DxgkDdiOPMGetInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_STATUS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>