---
UID : NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
title : D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
author : windows-driver-content
description : D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 is used with VideoDecoderSubmitBuffers1 to submit one or more buffer for decoding.
old-location : display\d3dwddm2_0ddi_video_decoder_buffer_desc1.htm
old-project : display
ms.assetid : BF57E573-852E-4784-8E76-B5E7D86A57EB
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1, D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 structure [Display Devices], display.d3dwddm2_0ddi_video_decoder_buffer_desc1, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.typenames : D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1
---

# D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 structure
<b>D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</b> is used with  <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecodersubmitbuffers1.md">VideoDecoderSubmitBuffers1</a> to submit one or more buffer for decoding.

## Syntax
````
typedef struct D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 {
  D3D10DDI_HRESOURCE                                                                           hResource;
  D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE                                                         BufferType;
  UINT                                                                                         DataOffset;
  UINT                                                                                         DataSize;
  _Field_size_opt_(IVSize) void                                                                *pIV;
  UINT                                                                                         IVSize;
  _Field_size_opt_(SubSampleMappingCount) D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK *pSubSampleMappingBlock;
  UINT                                                                                         SubSampleMappingCount;
} D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1;
````

## Members


`BufferType`

The type of buffer, specified as a member of the <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> enumeration.

`DataOffset`

The offset of the relevant data from the beginning of the buffer, in bytes. 
<div class="alert"><b>Important</b>  This value must be zero.</div><div> </div>

`DataSize`

Size of the relevant data.

`hResource`

A handle to the resource object that was created through a call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>.

`IVSize`

The size of the buffer specified in the <b>pIV</b> member. If <b>pIV</b> is <b>NULL</b>, set this member to zero.

`pIV`

A pointer to a buffer that contains an initialization vector (IV) for encrypted data. If the decode buffer does not contain encrypted data, set this member to <b>NULL</b>.

`pSubSampleMappingBlock`

A pointer to an array of <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block.md">D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</a> structures, which indicate exactly which bytes in the decode buffer are encrypted and which are in the clear.  If the decode buffer does not contain encrypted data, set this member to <b>NULL</b>.



Values in the sub sample mapping blocks are relative to the start of the decode buffer.

`SubSampleMappingCount`

The number of <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block.md">D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</a> structures specified in the <b>pSubSampleMappingBlocks</b> member. If <b>pSubSampleMappingBLocks</b> is <b>NULL</b>, set this member to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_sub_sample_mapping_block.md">D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>