---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
title: "_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path.
old-location: display\d3dkmdt_vidpn_present_path_importance.htm
old-project: display
ms.assetid: a48eda3c-84cb-4413-a325-79c330be3f18
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/D3DKMDT_VPPI_SECONDARY, d3dkmdt/D3DKMDT_VPPI_DENARY, d3dkmdt/D3DKMDT_VPPI_PRIMARY, D3DKMDT_VPPI_QUATERNARY, D3DKMDT_VPPI_NONARY, D3DKMDT_VPPI_SECONDARY, D3DKMDT_VPPI_TERTIARY, D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, D3DKMDT_VPPI_SENARY, D3DKMDT_VPPI_OCTONARY, D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration [Display Devices], d3dkmdt/D3DKMDT_VPPI_UNINITIALIZED, D3DKMDT_VPPI_DENARY, D3DKMDT_VPPI_QUINARY, D3DKMDT_VPPI_PRIMARY, d3dkmdt/D3DKMDT_VPPI_SEPTENARY, d3dkmdt/D3DKMDT_VPPI_OCTONARY, d3dkmdt/D3DKMDT_VPPI_QUINARY, display.d3dkmdt_vidpn_present_path_importance, _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, d3dkmdt/D3DKMDT_VPPI_QUATERNARY, DmEnums_711fdb2d-86cd-4ac4-9529-818b3953dff5.xml, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, d3dkmdt/D3DKMDT_VPPI_SENARY, D3DKMDT_VPPI_SEPTENARY, d3dkmdt/D3DKMDT_VPPI_TERTIARY, D3DKMDT_VPPI_UNINITIALIZED, d3dkmdt/D3DKMDT_VPPI_NONARY
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
-	D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
---

# _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE Enumeration
The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path.

## Syntax
````
typedef enum _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE { 
  D3DKMDT_VPPI_UNINITIALIZED  = 0,
  D3DKMDT_VPPI_PRIMARY        = 1,
  D3DKMDT_VPPI_SECONDARY      = 2,
  D3DKMDT_VPPI_TERTIARY       = 3,
  D3DKMDT_VPPI_QUATERNARY     = 4,
  D3DKMDT_VPPI_QUINARY        = 5,
  D3DKMDT_VPPI_SENARY         = 6,
  D3DKMDT_VPPI_SEPTENARY      = 7,
  D3DKMDT_VPPI_OCTONARY       = 8,
  D3DKMDT_VPPI_NONARY         = 9,
  D3DKMDT_VPPI_DENARY         = 10
} D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMDT_VPPI_DENARY</td>
                    <td>Indicates importance level 10.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_NONARY</td>
                    <td>Indicates importance level 9.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_OCTONARY</td>
                    <td>Indicates importance level 8.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_PRIMARY</td>
                    <td>Indicates importance level 1.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_QUATERNARY</td>
                    <td>Indicates importance level 4.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_QUINARY</td>
                    <td>Indicates importance level 5.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_SECONDARY</td>
                    <td>Indicates importance level 2.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_SENARY</td>
                    <td>Indicates importance level 6.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_SEPTENARY</td>
                    <td>Indicates importance level 7.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_TERTIARY</td>
                    <td>Indicates importance level 3.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VPPI_UNINITIALIZED</td>
                    <td>Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE has not yet been assigned a meaningful value.</td>
                </tr>
</table>

    ## Remarks

        As the numeric value of a D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE value increases, the importance decreases. For example, level 3 is less important than level 2.

A variable of type D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE can have any integer value in the range 0 through 255, but only the values 0 through 10 have names.

It is useful to rank the video present paths in a video present network (VidPN) according to importance. For example, a path that represents the primary view can be assigned a higher importance than other paths so that it gets the best source and target mode sets.

The <b>ImportanceOrdinal</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE value. Path importance ordinal numbers are unique within a given VidPN topology.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>