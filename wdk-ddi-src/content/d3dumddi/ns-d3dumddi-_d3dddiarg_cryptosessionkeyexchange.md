---
UID : NS:d3dumddi._D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
title : "_D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE"
author : windows-driver-content
description : The D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure describes a buffer that contains the session key, which is used for encryption.
old-location : display\d3dddiarg_cryptosessionkeyexchange.htm
old-project : display
ms.assetid : 45ff38bf-7640-4b7c-ab26-ae758c9b4696
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure [Display Devices], D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, UMDisplayDriver_param_Structs_80a0e3f6-7fa5-444f-9eeb-505a6632af8d.xml, _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, display.d3dddiarg_cryptosessionkeyexchange
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
---

# _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure
The D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure describes a buffer that contains the session key, which is used for encryption.

## Syntax
````
typedef struct _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE {
  HANDLE hCryptoSession;
  UINT   DataSize;
  VOID   *pData;
} D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE;
````

## Members


`DataSize`

[in/out] The size, in bytes, of the data that the <b>pData</b> member points to.

`hCryptoSession`

[in] A handle to the encryption session that is the runtime creates when the runtime calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function.

`pData`

[in/out] A pointer to a buffer that contains the session key.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system. D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>