---
UID: NE:dxva._DXVA_ProcAmpControlProp
title: "_DXVA_ProcAmpControlProp"
author: windows-driver-content
description: The DXVA_ProcAmpControlProp enumeration is used to determine the required ProcAmp control adjustments.
old-location: display\dxva_procampcontrolprop.htm
old-project: display
ms.assetid: ce1bae9b-1cc3-45ea-bf46-8aa7ed0362f6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA_ProcAmpControlProp, DXVA_ProcAmpControlProp enumeration [Display Devices], DXVA_ProcAmp_Brightness, DXVA_ProcAmp_Contrast, DXVA_ProcAmp_Hue, DXVA_ProcAmp_None, DXVA_ProcAmp_Saturation, _DXVA_ProcAmpControlProp, display.dxva_procampcontrolprop, dxva/DXVA_ProcAmpControlProp, dxva/DXVA_ProcAmp_Brightness, dxva/DXVA_ProcAmp_Contrast, dxva/DXVA_ProcAmp_Hue, dxva/DXVA_ProcAmp_None, dxva/DXVA_ProcAmp_Saturation, dxvaref_0bce43bc-3bb3-4c7a-8d83-16db2a513905.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_ProcAmpControlProp
product:
- Windows
targetos: Windows
req.typenames: DXVA_ProcAmpControlProp
---

# _DXVA_ProcAmpControlProp Enumeration
The DXVA_ProcAmpControlProp enumeration is used to determine the required ProcAmp control adjustments.

## Syntax
```
typedef enum _DXVA_ProcAmpControlProp {
  DXVA_ProcAmp_None        ,
  DXVA_ProcAmp_Brightness  ,
  DXVA_ProcAmp_Contrast    ,
  DXVA_ProcAmp_Hue         ,
  DXVA_ProcAmp_Saturation
} DXVA_ProcAmpControlProp;
```

## Constants

<table>
            
                <tr>
                    <td>DXVA_ProcAmp_None</td>
                    <td>Specifies that no ProcAmp properties are used.</td>
                </tr>
            
                <tr>
                    <td>DXVA_ProcAmp_Brightness</td>
                    <td>Specifies that the ProcAmp brightness property is used.</td>
                </tr>
            
                <tr>
                    <td>DXVA_ProcAmp_Contrast</td>
                    <td>Specifies that the ProcAmp contrast property is used.</td>
                </tr>
            
                <tr>
                    <td>DXVA_ProcAmp_Hue</td>
                    <td>Specifies that the ProcAmp hue property is used.</td>
                </tr>
            
                <tr>
                    <td>DXVA_ProcAmp_Saturation</td>
                    <td>Specifies that the ProcAmp saturation property is used.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DirectX 9.0 and later versions only. DirectX 9.0 and later versions only. |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564019">DXVA_ProcAmpControlCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564032">DXVA_ProcAmpControlQueryRange</a>