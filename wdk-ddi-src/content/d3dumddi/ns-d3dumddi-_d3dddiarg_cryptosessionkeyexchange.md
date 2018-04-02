---
UID: NS:d3dumddi._D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
title: "_D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE"
author: windows-driver-content
description: The D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure describes a buffer that contains the session key, which is used for encryption.
old-location: display\d3dddiarg_cryptosessionkeyexchange.htm
old-project: display
ms.assetid: 45ff38bf-7640-4b7c-ab26-ae758c9b4696
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure [Display Devices], UMDisplayDriver_param_Structs_80a0e3f6-7fa5-444f-9eeb-505a6632af8d.xml, _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, d3dumddi/D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, display.d3dddiarg_cryptosessionkeyexchange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
---

# _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure
The D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure describes a buffer that contains the session key, which is used for encryption.

## Syntax
```
typedef struct _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE {
  HANDLE hCryptoSession;
  UINT   DataSize;
  VOID   *pData;
} D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE;
```

## Members


`hCryptoSession`

[in] A handle to the encryption session that is the runtime creates when the runtime calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.

`DataSize`

[in/out] The size, in bytes, of the data that the <b>pData</b> member points to.

`pData`

[in/out] A pointer to a buffer that contains the session key.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system. D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>