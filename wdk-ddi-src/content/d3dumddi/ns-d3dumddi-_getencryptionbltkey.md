---
UID: NS.D3DUMDDI._GETENCRYPTIONBLTKEY
title: _GETENCRYPTIONBLTKEY
author: windows-driver-content
description: The D3DDDIARG_GETENCRYPTIONBLTKEY structure describes an encrypted bit-block transfer (bitblt) session for which the GetEncryptionBltKey function retrieves the encryption key.
old-location: display\d3dddiarg_getencryptionbltkey.htm
old-project: display
ms.assetid: 6f481646-b665-46cb-b551-10515b8603c5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _GETENCRYPTIONBLTKEY, D3DDDIARG_GETENCRYPTIONBLTKEY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_GETENCRYPTIONBLTKEY is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_GETENCRYPTIONBLTKEY
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
---

# _GETENCRYPTIONBLTKEY structure



## -description
The D3DDDIARG_GETENCRYPTIONBLTKEY structure describes an encrypted bit-block transfer (bitblt) session for which the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getencryptionbltkey.md">GetEncryptionBltKey</a> function retrieves the encryption key. 


## -syntax

````
typedef struct _GETENCRYPTIONBLTKEY {
  HANDLE hCryptoSession;
  VOID   *pReadBackKey;
  UINT   KeySize;
} D3DDDIARG_GETENCRYPTIONBLTKEY;
````


## -struct-fields

### -field hCryptoSession

[in] A handle to the encryption session that is created in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function. 

### -field pReadBackKey

[in] A pointer to a buffer that contains the encryption key. 

### -field KeySize

[in] The size, in bytes, of the encryption key that the <b>pReadBackKey</b> member points to. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
D3DDDIARG_GETENCRYPTIONBLTKEY is supported beginning with the Windows 7 operating system.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getencryptionbltkey.md">GetEncryptionBltKey</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GETENCRYPTIONBLTKEY structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
