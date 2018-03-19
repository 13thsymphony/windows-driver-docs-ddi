---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC
title: D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC
author: windows-driver-content
description: Describes a compressed buffer for Microsoft DirectX Video Acceleration (DXVA) decoding.
old-location: display\d3d11_1ddi_video_decoderr_buffer_desc.htm
old-project: display
ms.assetid: aff44ad9-7ade-4b01-8e41-11d686728faa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC, D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure [Display Devices], D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC, D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC, display.d3d11_1ddi_video_decoderr_buffer_desc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC
---

# D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC structure
Describes a compressed buffer for Microsoft DirectX Video Acceleration (DXVA) decoding.

## Syntax
````
typedef struct D3D11_1DDI_VIDEO_DECODERR_BUFFER_DESC {
  D3D10DDI_HRESOURCE                   hResource;
  D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE BufferType;
  UINT                                 BufferIndex;
  UINT                                 DataOffset;
  UINT                                 DataSize;
  UINT                                 FirstMBaddress;
  UINT                                 NumMBsInBuffer;
  UINT                                 Width;
  UINT                                 Height;
  UINT                                 Stride;
  UINT                                 ReservedBits;
  void                                 *pIV;
  UINT                                 IVSize;
  BOOL                                 PartialEncryption;
  D3D11_1DDI_ENCRYPTED_BLOCK_INFO      EncryptedBlockInfo;
} D3D11_1DDI_VIDEO_DECODER_BUFFER_DESC;
````

## Members


`hResource`

A handle to the resource that will receive the decrypted and decode frame buffers.

`BufferType`

The type of buffer, specified as a constant value of the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> enumeration.

In D3d10umddi.h, <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> and <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> are defined as the same type.

`BufferIndex`

Reserved for system use.

`DataOffset`

The offset of the relevant data from the beginning of the buffer, in bytes. This value must be zero.

`DataSize`

The offset of the relevant data from the beginning of the buffer, in bytes. This value must be zero.

`FirstMBaddress`

The macroblock address of the first macroblock in the buffer. The macroblock address is given in raster scan order.

`NumMBsInBuffer`

The number of macroblocks of data in the buffer. This count includes skipped macroblocks.

`Width`

Reserved for system use. Set to zero.

`Height`

Reserved for system use. Set to zero.

`Stride`

Reserved for system use. Set to zero.

`ReservedBits`

Reserved for system use. Set to zero.

`pIV`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a> structure that contains an initialization vector (IV) for the frame buffer data that was encrypted by using the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption algorithm.

If the decode buffer does not contain any encrypted data, set <b>pIV</b> to <b>NULL</b>.

`IVSize`

The size of the buffer specified in the <b>pIV</b> member. If <b>pIV</b> is <b>NULL</b>, set this member to zero.

`PartialEncryption`

If <b>TRUE</b>, the video surfaces are partially encrypted.

`EncryptedBlockInfo`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that specifies which bytes of the surface are encrypted.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv.md">D3D11_1DDI_AES_CTR_IV</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_encrypted_block_info.md">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a>