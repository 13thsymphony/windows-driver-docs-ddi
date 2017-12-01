---
UID: NC.d3dumddi.PFND3DDDI_DECRYPTIONBLT
title: PFND3DDDI_DECRYPTIONBLT
author: windows-driver-content
description: The DecryptionBlt function writes data to a protected surface.
old-location: display\decryptionblt.htm
old-project: display
ms.assetid: 1bfe2b9c-90f6-48bf-b0b3-30788ef94110
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DecryptionBlt is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DecryptionBlt
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
req.iface: 
---

# PFND3DDDI_DECRYPTIONBLT callback



## -description
<p>The <b>DecryptionBlt</b> function writes data to a protected surface. </p>


## -prototype

````
PFND3DDDI_DECRYPTIONBLT DecryptionBlt;

__checkReturn HRESULT APIENTRY DecryptionBlt(
  _In_       HANDLE                  hDevice,
  _In_ const D3DDDIARG_DECRYPTIONBLT *pData
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context). </p>
</dd>

### -param <i>pData</i> [in]

<dd>
<p> A pointer to a <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> structure that describes the parameters of the decrypted bit-block transfer (bitblt) operation. </p>
</dd>
</dl>

## -returns
<p><b>DecryptionBlt</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The decrypted bitblt operation is successfully performed. </p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-decryptionblt.md">DecryptionBlt</a> could not allocate the required memory for it to complete.</p><dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl><p>The driver does not support the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-decryptionblt.md">DecryptionBlt</a> function. </p>

<p> </p>

## -remarks
<p>Hardware and drivers can optionally support <b>DecryptionBlt</b> for some crypto types. </p>

<p>If the calling application requires the use of a content key, the application uses the content key to encrypt the data, and the session key to encrypt the content key before passing the content key in the block of memory that the <b>pContentKey</b> member of <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> points to. If <b>pContentKey</b> is <b>NULL</b>, it indicates that the application used the session key to encrypt the data.</p>

<p>If the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createcryptosession.md">CreateCryptoSession</a> function previously created the encryption session with the <b>CryptoType</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a> structure set to D3DCRYPTOTYPE_AES128_CTR, the <b>pIV</b> member of <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> points to the <a href="display.dxvaddi_pvp_hw_iv">DXVADDI_PVP_HW_IV</a> structure and contains the initialization vector that the application used to encrypt the buffer. The driver's <b>DecryptionBlt</b> function should fail if it determines that the initialization vector was previously used for the same content key (or session key if the content key is not used). The application should increment the <b>IV</b> member of the DXVADDI_PVP_HW_IV structure for each buffer that the application encrypts. Therefore, the driver's <b>DecryptionBlt</b> function can fail if the <b>IV</b> member is less than or equal to the previous <b>IV</b> value that was passed to <b>DecryptionBlt</b>.</p>

<p>If the driver and hardware support partially encrypted buffers, the <b>pEncryptedBlockInfo</b> member of <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> indicates the portions of the buffer that are encrypted and the portions that are not encrypted.  If the entire buffer is encrypted, <b>pEncryptedBlockInfo</b> should be <b>NULL</b>.</p>

<p><b>DecryptionBlt</b> cannot write sub-rectangles.</p>

<p>The Direct3D runtime verifies that the source surface specified by the <b>SrcSubResourceIndex</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> structure is in system memory and that no stretching, colorspace conversion, and so on is performed. An application should ensure that the system memory buffer is properly aligned and that the buffer's size matches the destination surface. The driver should verify the memory alignment and the buffer size (<b>SrcResourceSize</b> member of D3DDDIARG_DECRYPTIONBLT) and fail if these conditions are not correct..</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p><i>DecryptionBlt</i> is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createcryptosession.md">CreateCryptoSession</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddi-devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DECRYPTIONBLT callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
