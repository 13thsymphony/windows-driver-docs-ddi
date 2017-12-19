---
UID: NS.D3DUMDDI._DXVADDI_EXTENDEDFORMAT
title: _DXVADDI_EXTENDEDFORMAT
author: windows-driver-content
description: The DXVADDI_EXTENDEDFORMAT structure describes the extended format of the video frame.
old-location: display\dxvaddi_extendedformat.htm
old-project: display
ms.assetid: e4f863bd-12ec-489d-a6e0-6b9242fbb0b0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXVADDI_EXTENDEDFORMAT, DXVADDI_EXTENDEDFORMAT
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
req.alt-api: DXVADDI_EXTENDEDFORMAT
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

# _DXVADDI_EXTENDEDFORMAT structure



## -description
The DXVADDI_EXTENDEDFORMAT structure describes the extended format of the video frame. 



## -syntax

````
typedef struct _DXVADDI_EXTENDEDFORMAT {
  union {
    struct {
      UINT SampleFormat  :8;
      UINT VideoChromaSubsampling  :4;
      UINT NominalRange  :3;
      UINT VideoTransferMatrix  :3;
      UINT VideoLighting  :4;
      UINT VideoPrimaries  :5;
      UINT VideoTransferFunction  :5;
    };
    UINT   Value;
  };
} DXVADDI_EXTENDEDFORMAT;
````


## -struct-fields

### -field SampleFormat

[in] A UINT value that specifies how a video frame is sampled. The eight bits are defined by one of the values in the <a href="display.dxvaddi_sampleformat">DXVADDI_SAMPLEFORMAT</a> enumeration type.


### -field VideoChromaSubsampling

[in] The chroma encoding scheme for Y'Cb'Cr' data. The four bits are defined by a bitwise OR of the values in the <a href="display.dxvaddi_videochromasubsampling">DXVADDI_VIDEOCHROMASUBSAMPLING</a> enumeration type. 


### -field NominalRange

[in] A UINT value that specifies whether sample data includes headroom (that is, values beyond 1.0 white) and toeroom (that is, superblacks below the reference 0.0 black). The three bits are defined by one of the values in the <a href="display.dxvaddi_nominalrange">DXVADDI_NOMINALRANGE</a> enumeration type. 


### -field VideoTransferMatrix

[in] The conversion matrix from Y'Cb'Cr' to (studio) R'G'B'. The three bits are defined by one of the values in the <a href="display.dxvaddi_videotransfermatrix">DXVADDI_VIDEOTRANSFERMATRIX</a> enumeration type. 


### -field VideoLighting

[in] Lighting conditions for viewing video. The four bits are defined by one of the values in the <a href="display.dxvaddi_videolighting">DXVADDI_VIDEOLIGHTING</a> enumeration type. 


### -field VideoPrimaries

[in] Color primaries, which state which RGB basis functions are used. The five bits are defined by one of the values in the <a href="display.dxvaddi_videoprimaries">DXVADDI_VIDEOPRIMARIES</a> enumeration type. 


### -field VideoTransferFunction

[in] The conversion function from R'G'B' to RGB. The five bits are defined by the <a href="display.dxvaddi_videotransferfunction">DXVADDI_VIDEOTRANSFERFUNCTION</a> enumeration type. 


### -field Value

A 32-bit value that describes the extended format of the video frame.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="display.dxvaddi_videodesc">DXVADDI_VIDEODESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_EXTENDEDFORMAT structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

