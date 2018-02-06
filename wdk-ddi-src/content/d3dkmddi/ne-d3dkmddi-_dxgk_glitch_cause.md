---
UID: NE:d3dkmddi._DXGK_GLITCH_CAUSE
title: "_DXGK_GLITCH_CAUSE"
author: windows-driver-content
description: Enumeration that describes what caused a glitch during a SetTimingsFromVidPn call.
old-location: display\dxgk_glitch_cause.htm
old-project: display
ms.assetid: A0356AE8-3A82-4722-9F46-8FE05646BF10
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_GLITCH_CAUSE_METADATA_CHANGE, DXGK_GLITCH_CAUSE enumeration [Display Devices], d3dkmddi/DXGK_GLITCH_CAUSE, DXGK_GLITCH_CAUSE_MEMORY_TIMING, d3dkmddi/DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE, DXGK_GLITCH_CAUSE_NONE, DXGK_GLITCH_CAUSE_PIPELINE_CHANGE, display.dxgk_glitch_cause, DXGK_GLITCH_CAUSE_TIMING_CHANGE, DXGK_GLITCH_CAUSE, d3dkmddi/DXGK_GLITCH_CAUSE_TIMING_CHANGE, DXGK_GLITCH_CAUSE_DRIVER_ERROR, d3dkmddi/DXGK_GLITCH_CAUSE_MEMORY_TIMING, _DXGK_GLITCH_CAUSE, d3dkmddi/DXGK_GLITCH_CAUSE_PIPELINE_CHANGE, d3dkmddi/DXGK_GLITCH_CAUSE_NONE, DXGK_GLITCH_CAUSE_ENCODER_RECONFIG, DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE, d3dkmddi/DXGK_GLITCH_CAUSE_METADATA_CHANGE, d3dkmddi/DXGK_GLITCH_CAUSE_DRIVER_ERROR, d3dkmddi/DXGK_GLITCH_CAUSE_ENCODER_RECONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_GLITCH_CAUSE
product: Windows
targetos: Windows
req.typenames: DXGK_GLITCH_CAUSE
---

# _DXGK_GLITCH_CAUSE Enumeration
Enumeration that describes what caused a glitch during a SetTimingsFromVidPn call.

## Syntax
````
typedef enum _DXGK_GLITCH_CAUSE { 
  DXGK_GLITCH_CAUSE_DRIVER_ERROR         = 0,
  DXGK_GLITCH_CAUSE_TIMING_CHANGE        = 1,
  DXGK_GLITCH_CAUSE_PIPELINE_CHANGE      = 2,
  DXGK_GLITCH_CAUSE_MEMORY_TIMING        = 3,
  DXGK_GLITCH_CAUSE_ENCODER_RECONFIG     = 4,
  DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE  = 5,
  DXGK_GLITCH_CAUSE_METADATA_CHANGE      = 6,
  DXGK_GLITCH_CAUSE_NONE                 = 255
} DXGK_GLITCH_CAUSE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_DRIVER_ERROR</td>
                    <td>Indicates that an internal driver error caused a glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_ENCODER_RECONFIG</td>
                    <td>Indicates that changing the configuration of the encoder for a target caused a glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_MEMORY_TIMING</td>
                    <td>Indicates that changing graphics memory timings caused a glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_METADATA_CHANGE</td>
                    <td>Indicates that changing the frame metadata caused a glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_MODIFIED_WIRE_USAGE</td>
                    <td>Indicates that modifying the format of pixel data in the transport stream caused a glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_NONE</td>
                    <td>Indicates that there was no glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_PIPELINE_CHANGE</td>
                    <td>Indicates that reconfiguring the display pipeline caused a glitch.</td>
                </tr>
            
                <tr>
                    <td>DXGK_GLITCH_CAUSE_TIMING_CHANGE</td>
                    <td>Indicates that the timing requested necessitated a glitch.  This cause should only be used if the OS requested a change which would always result in a glitch rather than something which could have been avoided under other circumstances.  

For example, this should not be used if the driver switches to a different display pipe to support an additional path, but it should be used if the OS requests a different timing to the previous one.</td>
                </tr>
            
                <tr>
                    <td>UINT8</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |