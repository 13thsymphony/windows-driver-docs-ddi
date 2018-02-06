---
UID: NE:d3dkmdt._DXGKMDT_CERTIFICATE_TYPE
title: "_DXGKMDT_CERTIFICATE_TYPE"
author: windows-driver-content
description: The DXGKMDT_CERTIFICATE_TYPE enumeration identifies the type of certificate that callers of the DxgkDdiOPMGetCertificateSize and DxgkDdiOPMGetCertificate functions require.
old-location: display\dxgkmdt_certificate_type.htm
old-project: display
ms.assetid: aad96bf7-46d3-4859-b324-f48cdb99a594
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/DXGKMDT_CERTIFICATE_TYPE, DXGKMDT_COPP_CERTIFICATE, _DXGKMDT_CERTIFICATE_TYPE, DXGKMDT_CERTIFICATE_TYPE enumeration [Display Devices], DXGKMDT_UAB_CERTIFICATE, DXGKMDT_FORCE_ULONG, DXGKMDT_OPM_CERTIFICATE, d3dkmdt/DXGKMDT_UAB_CERTIFICATE, d3dkmdt/DXGKMDT_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_CERTIFICATE, d3dkmdt/DXGKMDT_COPP_CERTIFICATE, DmEnums_837195ed-375e-43ef-a854-1d1f0aab0c84.xml, DXGKMDT_CERTIFICATE_TYPE, display.dxgkmdt_certificate_type
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
-	DXGKMDT_CERTIFICATE_TYPE
product: Windows
targetos: Windows
req.typenames: DXGKMDT_CERTIFICATE_TYPE
---

# _DXGKMDT_CERTIFICATE_TYPE Enumeration
The DXGKMDT_CERTIFICATE_TYPE enumeration identifies the type of certificate that callers of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a> and <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate.md">DxgkDdiOPMGetCertificate</a> functions require.

## Syntax
````
typedef enum _DXGKMDT_CERTIFICATE_TYPE { 
  DXGKMDT_OPM_CERTIFICATE   = 0,
  DXGKMDT_COPP_CERTIFICATE  = 1,
  DXGKMDT_UAB_CERTIFICATE   = 2,
  DXGKMDT_FORCE_ULONG       = 0xFFFFFFFF
} DXGKMDT_CERTIFICATE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKMDT_COPP_CERTIFICATE</td>
                    <td>Indicates a Certified Output Protection Protocol (COPP) certificate.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_FORCE_ULONG</td>
                    <td>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_INDIRECT_DISPLAY_CERTIFICATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_OPM_CERTIFICATE</td>
                    <td>Indicates an Output Protection Management (OPM) certificate.</td>
                </tr>
            
                <tr>
                    <td>DXGKMDT_UAB_CERTIFICATE</td>
                    <td>Indicates a User Accessible Bus (UAB) certificate.</td>
                </tr>
</table>

    ## Remarks

        For more information about certificates that are used with OPM, download the Output Content Protection document at the <a href="http://go.microsoft.com/fwlink/p/?linkid=204788">Output Content Protection and Windows Vista</a> website.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate_size.md">DxgkDdiOPMGetCertificateSize</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_get_certificate.md">DxgkDdiOPMGetCertificate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_CERTIFICATE_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>