---
UID: NS:d3dkmthk._D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
title: _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
author: windows-driver-content
description: The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure identifies attributes of a flip present-history operation.
old-location: display\d3dkmt_flipmodel_presenthistorytokenflags.htm
old-project: display
ms.assetid: 61901e06-fefd-4481-9f19-60ead55bbe36
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS, D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS
---

# _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure



## -description
The D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure identifies attributes of a flip present-history operation.



## -syntax

````
typedef struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS {
  union {
    struct {
      UINT Video  :1;
      UINT RestrictedContent  :1;
      UINT ClipToView  :1;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
      UINT StereoPreferRight  :1;
      UINT TemporaryMono  :1;
      UINT FlipRestart  :1;
      UINT ScatterBlt  :1;
      UINT AlphaMode  :2;
      UINT SignalLimitOnTokenCompletion  :1;
      UINT Reserved  :22;
#else 
      UINT Reserved  :29;
#endif 
    };
    UINT   Value;
  };
} D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS;
````


## -struct-fields

### -field Video

A UINT value that specifies whether the flip operation is performed with video. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field RestrictedContent

A UINT value that specifies whether the flip operation is performed with restricted content.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field ClipToView

A UINT value that specifies whether the flip operation is clipped to the view surface.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field StereoPreferRight

A UINT value that specifies that when the driver clones a stereo primary allocation to a mono monitor, it should use the right image.

Setting this member is equivalent to setting the    fourth bit of the 32-bit <b>Value</b> member (0x00000008).

Supported starting with Windows 8.


### -field TemporaryMono

A UINT value that specifies whether the driver should use the left image of a stereo allocation for the right and left portions of a stereo frame.

This member should  be set only if the driver reports support for this option in the current display mode by setting the <b>Type</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_source_mode.md">D3DKMDT_VIDPN_SOURCE_MODE</a> structure to D3DKMDT_RMT_GRAPHICS_STEREO_ADVANCED_SCAN.

Setting this member is equivalent to setting the    fifth bit of the 32-bit <b>Value</b> member (0x00000010).

Supported starting with Windows 8.


### -field FlipRestart

A UINT value that specifies whether to restart a flip to a new surface.

Setting this member is equivalent to setting the    sixth bit of the 32-bit <b>Value</b> member (0x00000020).

Supported starting with Windows 8.


### -field ScatterBlt

This member is reserved for system use and should be set to zero.

Setting this member is equivalent to setting the    seventh bit of the 32-bit <b>Value</b> member (0x00000040).

Supported starting with Windows 8.


### -field AlphaMode

A UINT value that specifies whether the DWM  should use alpha transparency information when it composes swap buffers.

Setting this member is equivalent to setting the    eighth and ninth bits of the 32-bit <b>Value</b> member (0x00000180).

Supported starting with Windows 8.


### -field SignalLimitOnTokenCompletion

 A UINT value that specifies the limit for the number of present operations that can be queued for the device after the GPU has finished processing the token.

Setting this member is equivalent to setting the    tenth bit of the 32-bit <b>Value</b> member (0x00000200).

Supported starting with Windows 8.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 22 bits (0xFFFFFC00) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A 32-bit value that identifies the flip present-history operation.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

