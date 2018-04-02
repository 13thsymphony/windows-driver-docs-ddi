---
UID: NS:d3dumddi._DDICONTENTPROTECTIONCAPS
title: "_DDICONTENTPROTECTIONCAPS"
author: windows-driver-content
description: The DDICONTENTPROTECTIONCAPS structure describes a specific encryption and decode combination that the driver uses.
old-location: display\ddicontentprotectioncaps.htm
old-project: display
ms.assetid: d223712d-2c77-4bec-b8c0-d677d4caeac2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D_other_Structs_15111323-4ebe-49be-8ce6-d43a896533ee.xml, DDICONTENTPROTECTIONCAPS, DDICONTENTPROTECTIONCAPS structure [Display Devices], _DDICONTENTPROTECTIONCAPS, d3dumddi/DDICONTENTPROTECTIONCAPS, display.ddicontentprotectioncaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DDICONTENTPROTECTIONCAPS is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DDICONTENTPROTECTIONCAPS
product: Windows
targetos: Windows
req.typenames: DDICONTENTPROTECTIONCAPS
---

# _DDICONTENTPROTECTIONCAPS structure
The DDICONTENTPROTECTIONCAPS structure describes a specific encryption and decode combination that the driver uses.

## Syntax
```
typedef struct _DDICONTENTPROTECTIONCAPS {
  GUID CryptoType;
  GUID DecodeProfile;
} DDICONTENTPROTECTIONCAPS;
```

## Members


`CryptoType`

[in] A GUID that indicates the encryption type that the driver uses. The currently defined GUIDs are:





#### D3DCRYPTOTYPE_AES128_CTR

A GUID that indicates the 128-bit AES-CRT block cipher.



#### D3DCRYPTOTYPE_PROPRIETARY

A GUID that indicates a proprietary encryption algorithm. 

A <b>NULL</b> value indicates that no encryption is used.

`DecodeProfile`

[in] A GUID that indicates the DirectX Video Acceleration (DirectX VA) decode profile that the driver uses along with the encryption type, which the <b>CryptoType</b> member specifies. Not all drivers allow all types of encryption. For example, MPEG2 IDCT frequently requires that the private libraries, which the hardware vendor supplies, perform the proprietary encryption. A <b>NULL</b> value indicates that DirectX VA decode profile is not used.

## Remarks
The runtime specifies a pointer to a DDICONTENTPROTECTIONCAPS structure in the <b>pInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a> structure--along with the D3DDDICAPS_GETCONTENTPROTECTIONCAPS value in the <b>Type</b> member of D3DDDIARG_GETCAPS--in a call to the user-mode display driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function to determine the content-protection capabilities that the driver supports. The driver's <b>GetCaps</b> returns a pointer to a populated D3DCONTENTPROTECTIONCAPS structure in the <b>pData</b> member of D3DDDIARG_GETCAPS that describes the content-protection capabilities that the driver supports. An application calls the <b>IDirect3DDevice9Video::GetContentProtectionCaps</b> method to retrieve these content-protection capabilities. For more information about <b>IDirect3DDevice9Video::GetContentProtectionCaps</b> and D3DCONTENTPROTECTIONCAPS, see the DirectX SDK documentation.

If the runtime specifies NULL_GUID (all zeros) in <b>DecodeProfile</b>, the driver should return the content-protection capabilities that are relevant for when a DirectX VA decode profile is not used. These content-protection capabilities correspond to the content-protection DDI functions that the driver optionally implements. For more information about these optional functions, see <a href="https://msdn.microsoft.com/770e0fce-d3b5-4599-8165-eadf3f23f9dc">Content Protection DDI</a>.

If the encryption type that is specified in the <b>CryptoType</b> member is supported by the graphics hardware and the driver, but is not supported by the DirectX VA decode profile that is specified in the <b>DecodeProfile</b> member, the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function should return D3DDDIERR_UNSUPPORTEDCRYPTO. If the encryption type that is specified in the <b>CryptoType</b> member is not supported at all, the driver's <b>GetCaps</b> function should return D3DDDIERR_NOTAVAILABLE.

If the runtime specifies NULL_GUID in the <b>CryptoType</b> member, the driver should report a superset of its content-protection capabilities. For example, if encryption type A supports some capabilities and encryption type B supports some other capabilities, the driver should return the cumulative capabilities.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DDICONTENTPROTECTIONCAPS is supported beginning with the Windows 7 operating system. DDICONTENTPROTECTIONCAPS is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543148">D3DDDIARG_GETCAPS</a>



<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>