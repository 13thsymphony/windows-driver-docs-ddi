---
UID: NE.d3dkmthk._QAI_DRIVERVERSION
title: _QAI_DRIVERVERSION
author: windows-driver-content
description: The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports.
old-location: display\d3dkmt_driverversion.htm
old-project: display
ms.assetid: 12ac73ed-f829-4f22-bca9-ccc1dc29f4c4
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _QAI_DRIVERVERSION, D3DKMT_DRIVERVERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_DRIVERVERSION is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_DRIVERVERSION
req.alt-loc: d3dkmthk.h
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
---

# _QAI_DRIVERVERSION enumeration



## -description
The D3DKMT_DRIVERVERSION enumeration type contains values that indicate the version of the display driver model that the display miniport driver supports.



## -syntax

````
typedef enum _QAI_DRIVERVERSION { 
  KMT_DRIVERVERSION_WDDM_1_0             = 1000,
  KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE  = 1102,
  KMT_DRIVERVERSION_WDDM_1_1             = 1105,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  KMT_DRIVERVERSION_WDDM_1_2             = 1200,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  KMT_DRIVERVERSION_WDDM_1_3             = 1300,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  KMT_DRIVERVERSION_WDDM_2_0             = 2000,
#endif 
  
} D3DKMT_DRIVERVERSION;
````


## -enum-fields

### -field KMT_DRIVERVERSION_WDDM_1_0

The display miniport driver supports the Windows Vista display driver model (WDDM) without Windows 7 features. 


### -field KMT_DRIVERVERSION_WDDM_1_1_PRERELEASE

The display miniport driver supports the Windows Vista display driver model with prereleased Windows 7 features. 


### -field KMT_DRIVERVERSION_WDDM_1_1

The display miniport driver supports the Windows Vista display driver model with released Windows 7 features. 


### -field KMT_DRIVERVERSION_WDDM_1_2

The display miniport driver supports the Windows Vista display driver model with released Windows 8 features.

Supported starting with Windows 8.


### -field KMT_DRIVERVERSION_WDDM_1_3

The display miniport driver supports the Windows display driver model with released Windows 8.1 features.

Supported starting with Windows 8.1.


### -field KMT_DRIVERVERSION_WDDM_2_0

The display miniport driver supports the Windows display driver model with released Windows 10 features.

Supported starting with Windows 10.


### -field 


## -remarks
The <a href="display.d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a> returns a D3DKMT_DRIVERVERSION value in a variable that the <b>pPrivateDriverData</b> member of the <a href="display.d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a> structure points to when the OpenGL installable client driver (ICD) sets the <b>Type</b> member of <b>D3DKMT_QUERYADAPTERINFO</b> to KMTQAITYPE_DRIVERVERSION.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3DKMT_DRIVERVERSION is supported beginning with the Windows 7 operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="display.d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DRIVERVERSION enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

