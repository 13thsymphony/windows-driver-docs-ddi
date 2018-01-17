---
UID: NS:d3dumddi._DXVADDI_PVP_HW_IV
title: _DXVADDI_PVP_HW_IV
author: windows-driver-content
description: The DXVADDI_PVP_HW_IV structure contains two 64-bit values that combine to form a 128-bit protected video path (PVP) value.
old-location: display\dxvaddi_pvp_hw_iv.htm
old-project: display
ms.assetid: 8ba29a38-1bf9-47a9-8da6-1f92eb8e8733
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVADDI_PVP_HW_IV, DXVADDI_PVP_HW_IV
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVADDI_PVP_HW_IV
req.alt-loc: d3dumddi.h
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
req.typenames: DXVADDI_PVP_HW_IV
---

# _DXVADDI_PVP_HW_IV structure



## -description
The DXVADDI_PVP_HW_IV structure contains two 64-bit values that combine to form a 128-bit protected video path (PVP) value.



## -syntax

````
typedef struct _DXVADDI_PVP_HW_IV {
  ULONGLONG IV;
  ULONGLONG Count;
} DXVADDI_PVP_HW_IV;
````


## -struct-fields

### -field IV

[in] A 64-bit initialization vector.


### -field Count

[in] A 64-bit number.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferdesc.md">DXVADDI_DECODEBUFFERDESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_PVP_HW_IV structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

