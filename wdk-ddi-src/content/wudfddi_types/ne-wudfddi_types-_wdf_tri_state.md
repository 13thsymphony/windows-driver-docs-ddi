---
UID: NE:wudfddi_types._WDF_TRI_STATE
title: "_WDF_TRI_STATE"
author: windows-driver-content
description: The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.
old-location: wdf\wdf_tri_state.htm
old-project: wdf
ms.assetid: 8ea6e373-225d-4fcd-abcf-c19b07f9f5d8
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdftypes/WdfUseDefault, PWDF_TRI_STATE, PWDF_TRI_STATE enumeration pointer, WdfTrue, wdftypes/WdfTrue, wudfddi_types/WdfTrue, kmdf.wdf_tri_state, wudfddi_types/WdfFalse, wudfddi_types/WDF_TRI_STATE, WdfFalse, wdftypes/WDF_TRI_STATE, wdftypes/WdfFalse, WDF_TRI_STATE enumeration, wudfddi_types/WdfUseDefault, wudfddi_types/PWDF_TRI_STATE, DFGenObjectRef_83855649-9d84-4f8c-9685-5e5321209b4d.xml, _WDF_TRI_STATE, *PWDF_TRI_STATE, wdftypes/PWDF_TRI_STATE, WDF_TRI_STATE, wdf.wdf_tri_state, WdfUseDefault
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdftypes.h
-	wudfddi_types.h
apiname:
-	WDF_TRI_STATE
product: Windows
targetos: Windows
req.typenames: "*PWDF_TRI_STATE, WDF_TRI_STATE"
req.product: Windows 10 or later.
---

# _WDF_TRI_STATE Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters.

## Syntax
````
typedef enum _WDF_TRI_STATE { 
  WdfFalse       = FALSE,
  WdfTrue        = TRUE,
  WdfUseDefault  = 2
} WDF_TRI_STATE, *PWDF_TRI_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WdfFalse</td>
                    <td>The meaning of this enumerator is specific to its use as a structure member or function parameter.</td>
                </tr>
            
                <tr>
                    <td>WdfTrue</td>
                    <td>The meaning of this enumerator is specific to its use as a structure member or function parameter.</td>
                </tr>
            
                <tr>
                    <td>WdfUseDefault</td>
                    <td>The meaning of this enumerator is specific to its use as a structure member or function parameter.</td>
                </tr>
</table>

    ## Remarks

        The WDF_TRI_STATE enumeration type is available in version 1.0 and later versions of KMDF.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi_types.h (include Wdf.h) |