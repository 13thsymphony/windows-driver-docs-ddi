---
UID: NE:d3dkmddi._DXGK_QUERYADAPTERINFOTYPE
title: "_DXGK_QUERYADAPTERINFOTYPE"
author: windows-driver-content
description: The DXGK_QUERYADAPTERINFOTYPE enumeration indicates the type of information to retrieve.
old-location: display\dxgk_queryadapterinfotype.htm
old-project: display
ms.assetid: 5cceffb1-853c-4635-b855-d0e3f107c23d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKQAITYPE_ALLOCATIONGROUP, DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION, DXGKQAITYPE_DRIVERCAPS, DXGKQAITYPE_GPUMMUCAPS, DXGKQAITYPE_HISTORYBUFFERPRECISION, DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR, DXGKQAITYPE_NUMPOWERCOMPONENTS, DXGKQAITYPE_PAGETABLELEVELDESC, DXGKQAITYPE_PHYSICALADAPTERCAPS, DXGKQAITYPE_POWERCOMPONENTINFO, DXGKQAITYPE_POWERCOMPONENTPSTATEINFO, DXGKQAITYPE_PREFERREDGPUNODE, DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES, DXGKQAITYPE_QUERYSEGMENT, DXGKQAITYPE_QUERYSEGMENT2, DXGKQAITYPE_QUERYSEGMENT3, DXGKQAITYPE_QUERYSEGMENT4, DXGKQAITYPE_SEGMENTMEMORYSTATE, DXGKQAITYPE_UEFIFRAMEBUFFERRANGES, DXGKQAITYPE_UMDRIVERPRIVATE, DXGK_QUERYADAPTERINFOTYPE, DXGK_QUERYADAPTERINFOTYPE enumeration [Display Devices], DmEnums_c4637ac2-b8e0-4c30-a709-5a8ff1ee3fdc.xml, _DXGK_QUERYADAPTERINFOTYPE, d3dkmddi/DXGKQAITYPE_ALLOCATIONGROUP, d3dkmddi/DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION, d3dkmddi/DXGKQAITYPE_DRIVERCAPS, d3dkmddi/DXGKQAITYPE_GPUMMUCAPS, d3dkmddi/DXGKQAITYPE_HISTORYBUFFERPRECISION, d3dkmddi/DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR, d3dkmddi/DXGKQAITYPE_NUMPOWERCOMPONENTS, d3dkmddi/DXGKQAITYPE_PAGETABLELEVELDESC, d3dkmddi/DXGKQAITYPE_PHYSICALADAPTERCAPS, d3dkmddi/DXGKQAITYPE_POWERCOMPONENTINFO, d3dkmddi/DXGKQAITYPE_POWERCOMPONENTPSTATEINFO, d3dkmddi/DXGKQAITYPE_PREFERREDGPUNODE, d3dkmddi/DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT2, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT3, d3dkmddi/DXGKQAITYPE_QUERYSEGMENT4, d3dkmddi/DXGKQAITYPE_SEGMENTMEMORYSTATE, d3dkmddi/DXGKQAITYPE_UEFIFRAMEBUFFERRANGES, d3dkmddi/DXGKQAITYPE_UMDRIVERPRIVATE, d3dkmddi/DXGK_QUERYADAPTERINFOTYPE, display.dxgk_queryadapterinfotype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
-	d3dkmddi.h
api_name:
-	DXGK_QUERYADAPTERINFOTYPE
product: Windows
targetos: Windows
req.typenames: DXGK_QUERYADAPTERINFOTYPE
---

# _DXGK_QUERYADAPTERINFOTYPE Enumeration
The DXGK_QUERYADAPTERINFOTYPE enumeration indicates the type of information to retrieve.

## Syntax
````
typedef enum _DXGK_QUERYADAPTERINFOTYPE { 
  DXGKQAITYPE_UMDRIVERPRIVATE                   = 0,
  DXGKQAITYPE_DRIVERCAPS                        = 1,
  DXGKQAITYPE_QUERYSEGMENT                      = 2,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7)
  DXGKQAITYPE_ALLOCATIONGROUP                   = 3,
  DXGKQAITYPE_QUERYSEGMENT2                     = 4,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  DXGKQAITYPE_QUERYSEGMENT3                     = 5,
  DXGKQAITYPE_NUMPOWERCOMPONENTS                = 6,
  DXGKQAITYPE_POWERCOMPONENTINFO                = 7,
  DXGKQAITYPE_PREFERREDGPUNODE                  = 8,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  DXGKQAITYPE_POWERCOMPONENTPSTATEINFO          = 9,
  DXGKQAITYPE_HISTORYBUFFERPRECISION            = 10,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  DXGKQAITYPE_QUERYSEGMENT4                     = 11,
  DXGKQAITYPE_SEGMENTMEMORYSTATE                = 12,
  DXGKQAITYPE_GPUMMUCAPS                        = 13,
  DXGKQAITYPE_PAGETABLELEVELDESC                = 14,
  DXGKQAITYPE_PHYSICALADAPTERCAPS               = 15,
  DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION      = 16,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
  DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR     = 17,
  DXGKQAITYPE_UEFIFRAMEBUFFERRANGES             = 18,
  DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES         = 19
} DXGK_QUERYADAPTERINFOTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGKQAITYPE_DISPLAY_DRIVERCAPS_EXTENSION</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_DISPLAYID_DESCRIPTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_DRIVERCAPS</td>
                    <td>Indicates the driver capabilities in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_GPUMMUCAPS</td>
                    <td>Indicates physical adapter GPU capabilities.

Supported starting with Windows 10.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_HISTORYBUFFERPRECISION</td>
                    <td>Indicates info about the precision of history buffer data used by the display miniport driver. For more information, see Remarks.

Supported starting with Windows 8.1.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_INTEGRATED_DISPLAY_DESCRIPTOR</td>
                    <td>Indicates a request for an integrated panel descriptor where the input buffer to the query will be a DXGK_QUERYINTEGRATEDDISPLAYIN structure and the output buffer is a DXGK_QUERYINTEGRATEDDISPLAYOUT structure.

Although this function addresses a target, only DxgKrnl adapter locks are taken over this call, not child device locks.  In practice, since this call will be made before the child device is exposed, there should be no concurrent DDI calls which address the same target.

<div class="alert"><b>Note</b>  Unlike most QueryAdapterInfo calls, the output buffer size is variable although it is still known in advance from the DescriptorLength field of the DXGK_INTEGRATED_DISPLAY_CHILD structure for the target id.  The size of the output buffer is:
DescriptorLength + FIELD_OFFSET( DXGK_QUERYINTEGRATEDDISPLAYOUT, Descriptor )
</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_NUMPOWERCOMPONENTS</td>
                    <td>Indicates the number of power components used by the display miniport driver.  For more information, see Remarks.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_PAGETABLELEVELDESC</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_PHYSICALADAPTERCAPS</td>
                    <td>Reserved for system use. Do not use in your driver.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_POWERCOMPONENTINFO</td>
                    <td>Indicates information about power components used by the display miniport driver. For more information, see Remarks.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_POWERCOMPONENTPSTATEINFO</td>
                    <td>Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.1.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_PREFERREDGPUNODE</td>
                    <td>Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_QUERYCOLORIMETRYOVERRIDES</td>
                    <td>Indicates a request for colorimetry overrides for an external display where the input buffer to the query will be a DXGK_QUERYCOLORIMETRYOVERRIDESIN structure, containing only the target id being addressed and the output buffer is a DXGK_COLORIMETRY structure into which the driver writes overrides for the monitor attached to the target.

Although this function addresses a target, only DxgKrnl adapter locks are taken over this call, not child device locks.  Since this call will be made before the child device is exposed, there should be no concurrent DDI calls which address the same target.

The output buffer is zeroed when passed to the driver.  If the driver has no overrides for the monitor, it should return STATUS_SUCCESS and leave the output buffer zeroed.  If the driver has overrides, it fill in all fields of the DXGK_COLORIMETRY to describe the monitor capabilities as the OS will not accept partial overrides.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_QUERYSEGMENT</td>
                    <td>Indicates memory-segment information in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_QUERYSEGMENT2</td>
                    <td>Reserved for system use. Do not use in your driver.
     Note that this constant occurs starting with Windows 7.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_QUERYSEGMENT3</td>
                    <td>Indicates memory-segment information in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a> structure.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_QUERYSEGMENT4</td>
                    <td>Indicates memory-segment information in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout4.md">DXGK_QUERYSEGMENTOUT4</a> structure.

Supported starting with Windows 10.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_RESERVED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_SEGMENTMEMORYSTATE</td>
                    <td>Indicates bad memory ranges in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_memoryrange.md">DXGK_MEMORYRANGE</a> structure. 

Supported starting with Windows 10.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_UEFIFRAMEBUFFERRANGES</td>
                    <td>Indicates request for the UEFI frame buffer ranges.</td>
                </tr>
            
                <tr>
                    <td>DXGKQAITYPE_UMDRIVERPRIVATE</td>
                    <td>Indicates private data for the user-mode display driver.</td>
                </tr>
</table>

## Remarks

The display miniport driver must fill the buffer pointed to by the <b>pOutputData</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure as follows:

<table>
<tr>
<th>Value of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>Type</b></th>
<th>Contents of output buffer pointed to by <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pOutputData</b></th>
</tr>
<tr>
<td><b>DXGKQAITYPE_UMDRIVERPRIVATE</b></td>
<td>Proprietary buffer</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_DRIVERCAPS</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_QUERYSEGMENT3</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a> structure</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_NUMPOWERCOMPONENTS</b></td>
<td>A UINT value that specifies the number of power components used by the display miniport driver</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_POWERCOMPONENTINFO</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_runtime_component.md">DXGK_POWER_RUNTIME_COMPONENT</a> structure that provides information about the <i>n</i>th power component, where <i>n</i> is the component index specified by  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b>  in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function</td>
</tr>
<tr>
<td><b>DXGKQAITYPE_HISTORYBUFFERPRECISION</b></td>
<td>Populated <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a> structure</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout3.md">DXGK_QUERYSEGMENTOUT3</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_power_runtime_component.md">DXGK_POWER_RUNTIME_COMPONENT</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_historybufferprecision.md">DXGKARG_HISTORYBUFFERPRECISION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_QUERYADAPTERINFOTYPE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>