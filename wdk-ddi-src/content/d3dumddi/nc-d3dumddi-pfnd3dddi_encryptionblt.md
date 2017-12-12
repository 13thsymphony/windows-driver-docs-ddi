---
UID: NC.d3dumddi.PFND3DDDI_ENCRYPTIONBLT
title: PFND3DDDI_ENCRYPTIONBLT
author: windows-driver-content
description: The EncryptionBlt function reads encrypted data from a protected surface.
old-location: display\encryptionblt.htm
old-project: display
ms.assetid: a92bfff7-8af6-48c3-9e7f-95b9426aaaf2
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: EncryptionBlt is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EncryptionBlt
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

# PFND3DDDI_ENCRYPTIONBLT callback



## -description
The <i>EncryptionBlt</i> function reads encrypted data from a protected surface.



## -prototype

````
PFND3DDDI_ENCRYPTIONBLT EncryptionBlt;

__checkReturn HRESULT APIENTRY EncryptionBlt(
  _In_       HANDLE                  hDevice,
  _In_ const D3DDDIARG_ENCRYPTIONBLT *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context). 


### -param pData [in]

 A pointer to a <a href="display.d3dddiarg_encryptionblt">D3DDDIARG_ENCRYPTIONBLT</a> structure that describes the parameters of the encrypted bit-block transfer (bitblt) operation. 


## -returns
<i>EncryptionBlt</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The encrypted bitblt operation is successfully performed. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>EncryptionBlt</i> could not allocate the required memory for it to complete.
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>The driver does not support the <i>EncryptionBlt</i> function. 

 


## -remarks
Hardware and drivers can optionally support <i>EncryptionBlt</i>. Some hardware might also require to use a separate key to decrypt the data that is read back. The driver returns this key in a block of memory that the <b>pIV</b> member of <a href="display.d3dddiarg_encryptionblt">D3DDDIARG_ENCRYPTIONBLT</a> points to. 

If the driver and hardware use a separate key for the encryption bitblt, the application must recognize this fact and use the key. 

If the crypto type is D3DCRYPTOTYPE_AES128_CTR, <b>pIV</b> points to a D3DAES_CTR_IV structure that the application allocates. However, the actual contents of the D3DAES_CTR_IV structure are filled in by the driver and hardware. When the driver and hardware generate the first initialization vector, they should initialize the <b>IV</b> member of the D3DAES_CTR_IV structure to a random number (that is not too big). Each subsequent initialization vector should simply increment the <b>IV</b> member, which ensures that the <b>IV</b> always increases in value. This fact enables the application to validate that the same <b>IV</b> is never used multiple times with the same key pair.

<i>EncryptionBlt</i> cannot read back sub-rectangles. <i>EncryptionBlt</i> also cannot read back partially encrypted buffers because many of the hardware-based solutions do not allow non-encrypted reads from protected memory.

The Direct3D runtime verifies that the destination surface specified by the <b>DstSubResourceIndex</b> member of D3DDDIARG_ENCRYPTIONBLT is in system memory and that no stretching, colorspace conversion, and so on is performed. An application should ensure that the system memory buffer is properly aligned and that the buffer's size matches the source surface. The driver should verify the memory alignment and the buffer size (<b>DstResourceSize</b> member of D3DDDIARG_ENCRYPTIONBLT) and fail if these conditions are not correct.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
<i>EncryptionBlt</i> is supported beginning with the Windows 7 operating system.

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
<a href="display.d3dddiarg_encryptionblt">D3DDDIARG_ENCRYPTIONBLT</a>
</dt>
<dt>
<a href="display.d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_ENCRYPTIONBLT callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

