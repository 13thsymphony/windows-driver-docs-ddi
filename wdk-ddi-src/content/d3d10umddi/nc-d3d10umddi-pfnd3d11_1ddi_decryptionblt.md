---
UID: NC:d3d10umddi.PFND3D11_1DDI_DECRYPTIONBLT
title: PFND3D11_1DDI_DECRYPTIONBLT
author: windows-driver-content
description: Writes encrypted data to a protected surface.
old-location: display\decryptionblt1.htm
old-project: display
ms.assetid: 36aeb826-251e-404e-8ce3-6b2246ff07bc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.decryptionblt1, DecryptionBlt callback function [Display Devices], DecryptionBlt, PFND3D11_1DDI_DECRYPTIONBLT, PFND3D11_1DDI_DECRYPTIONBLT, d3d10umddi/DecryptionBlt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	DecryptionBlt
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_DECRYPTIONBLT callback function
Writes encrypted data to a protected surface. This function is called only if <b>D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT</b> is set in the <b>Caps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure.

## Syntax

```
PFND3D11_1DDI_DECRYPTIONBLT Pfnd3d111DdiDecryptionblt;

void Pfnd3d111DdiDecryptionblt(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  D3D10DDI_HRESOURCE hSrcResource,
  D3D10DDI_HRESOURCE hDstResource,
  CONST D3D11_1DDI_ENCRYPTED_BLOCK_INFO *pEncryptedBlockInfo,
  UINT ContentKeySize,
  CONST VOID *pContentKey,
  UINT IVSize,
  CONST VOID *pIV
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hCryptoSession`

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.

`hSrcResource`

A handle to the resource that contains the source data.

`hDstResource`

A pointer to the resource where the encrypted data is to be written.

`*pEncryptedBlockInfo`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that describes the portions of the buffer that are encrypted. 

<div class="alert"><b>Note</b>  If the entire buffer is encrypted, <i>pEncryptedBlockinfo</i> should be set to NULL.</div>
<div> </div>

`ContentKeySize`

The size, in bytes, of the content key.

`*pContentKey`

A pointer to a block of memory that contains the content key that is required to decrypt the bit-block transfer (bitblt) data.

If <i>pContentKey</i> is not set to NULL, the buffer data is encrypted by using the specified content key. The data for this key is encrypted by using the session key with the AES-ECB algorithm.

If <i>pContentKey</i> is NULL, the graphics adapter does not require a separate content key to decrypt the data. In this case, the session key is used to decrypt the data.

`IVSize`

The size, in bytes, of the initialization vector (IV).

`*pIV`

A pointer to a block of memory that contains the initialization vector that is required to decrypt the bitblt data. For more information, see the Remarks section.

<div class="alert"><b>Note</b>  <p class="note">If <i>pIV</i> is NULL, the graphics adapter does not require a separate initialization vector to decrypt the data. That is, the session key is used to decrypt the data. 


</div>
<div> </div>


## Return Value

This callback function does not return a value.

## Remarks

For 128-bit AES-CTR encryption, the <i>pIV</i> parameter points to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a> structure that is allocated by the application. However, the actual contents of this structure are filled in by the driver or graphics adapter.  When the first IV is generated, the driver or adapter  initializes the <b>IV</b> member of this structure to a random number. For each subsequent IV, the caller increments the <b>IV</b> member, ensuring that the value always increases. This procedure enables the application to validate that the same IV is never used more than once with the same key pair.



For other encryption types, a different structure might be used, or the encryption might not use an IV.



<div class="alert"><b>Note</b>  This function does not honor a Direct3D version 11 predicate that may have been set.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_DECRYPTIONBLT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>