---
UID: NE:d3dkmdt._D3DKMDT_VIDEO_SIGNAL_STANDARD
title: _D3DKMDT_VIDEO_SIGNAL_STANDARD
author: windows-driver-content
description: The D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration contains constants that represent video signal standards.
old-location: display\d3dkmdt_video_signal_standard.htm
old-project: display
ms.assetid: bb129e02-ae01-4bbc-a81f-809f1a27060c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_VIDEO_SIGNAL_STANDARD, D3DKMDT_VIDEO_SIGNAL_STANDARD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDEO_SIGNAL_STANDARD
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: D3DKMDT_VIDEO_SIGNAL_STANDARD
---

# _D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration



## -description
The D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration contains constants that represent video signal standards.



## -syntax

````
typedef enum _D3DKMDT_VIDEO_SIGNAL_STANDARD { 
  D3DKMDT_VSS_UNINITIALIZED  = 0,
  D3DKMDT_VSS_VESA_DMT       = 1,
  D3DKMDT_VSS_VESA_GTF       = 2,
  D3DKMDT_VSS_VESA_CVT       = 3,
  D3DKMDT_VSS_IBM            = 4,
  D3DKMDT_VSS_APPLE          = 5,
  D3DKMDT_VSS_NTSC_M         = 6,
  D3DKMDT_VSS_NTSC_J         = 7,
  D3DKMDT_VSS_NTSC_443       = 8,
  D3DKMDT_VSS_PAL_B          = 9,
  D3DKMDT_VSS_PAL_B1         = 10,
  D3DKMDT_VSS_PAL_G          = 11,
  D3DKMDT_VSS_PAL_H          = 12,
  D3DKMDT_VSS_PAL_I          = 13,
  D3DKMDT_VSS_PAL_D          = 14,
  D3DKMDT_VSS_PAL_N          = 15,
  D3DKMDT_VSS_PAL_NC         = 16,
  D3DKMDT_VSS_SECAM_B        = 17,
  D3DKMDT_VSS_SECAM_D        = 18,
  D3DKMDT_VSS_SECAM_G        = 19,
  D3DKMDT_VSS_SECAM_H        = 20,
  D3DKMDT_VSS_SECAM_K        = 21,
  D3DKMDT_VSS_SECAM_K1       = 22,
  D3DKMDT_VSS_SECAM_L        = 23,
  D3DKMDT_VSS_SECAM_L1       = 24,
  D3DKMDT_VSS_EIA_861        = 25,
  D3DKMDT_VSS_EIA_861A       = 26,
  D3DKMDT_VSS_EIA_861B       = 27,
  D3DKMDT_VSS_PAL_K          = 28,
  D3DKMDT_VSS_PAL_K1         = 29,
  D3DKMDT_VSS_PAL_L          = 30,
  D3DKMDT_VSS_PAL_M          = 31,
  D3DKMDT_VSS_OTHER          = 255
} D3DKMDT_VIDEO_SIGNAL_STANDARD;
````


## -enum-fields

### -field D3DKMDT_VSS_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDEO_SIGNAL_STANDARD has not yet been assigned a meaningful value.


### -field D3DKMDT_VSS_VESA_DMT

Represents the Video Electronics Standards Association (VESA) Display Monitor Timing (DMT) standard.


### -field D3DKMDT_VSS_VESA_GTF

Represents the VESA Generalized Timing Formula (GTF) standard.


### -field D3DKMDT_VSS_VESA_CVT

Represents the VESA Coordinated Video Timing (CVT) standard.


### -field D3DKMDT_VSS_IBM

Represents the IBM standard.


### -field D3DKMDT_VSS_APPLE

Represents the Apple standard.


### -field D3DKMDT_VSS_NTSC_M

Represents the National Television Standards Committee (NTSC) standard.


### -field D3DKMDT_VSS_NTSC_J

Represents the NTSC standard.


### -field D3DKMDT_VSS_NTSC_443

Represents the NTSC standard.


### -field D3DKMDT_VSS_PAL_B

Represents the Phase Alteration Line (PAL) standard.


### -field D3DKMDT_VSS_PAL_B1

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_G

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_H

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_I

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_D

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_N

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_NC

Represents the PAL standard.


### -field D3DKMDT_VSS_SECAM_B

Represents the Systeme Electronic Pour Couleur Avec Memoire (SECAM) standard.


### -field D3DKMDT_VSS_SECAM_D

Represents the SECAM standard.


### -field D3DKMDT_VSS_SECAM_G

Represents the SECAM standard.


### -field D3DKMDT_VSS_SECAM_H

Represents the SECAM standard.


### -field D3DKMDT_VSS_SECAM_K

Represents the SECAM standard.


### -field D3DKMDT_VSS_SECAM_K1

Represents the SECAM standard.


### -field D3DKMDT_VSS_SECAM_L

Represents the SECAM standard.


### -field D3DKMDT_VSS_SECAM_L1

Represents the SECAM standard.


### -field D3DKMDT_VSS_EIA_861

Represents the Electronics Industries Association (EIA) standard.


### -field D3DKMDT_VSS_EIA_861A

Represents the EIA standard.


### -field D3DKMDT_VSS_EIA_861B

Represents the EIA standard.


### -field D3DKMDT_VSS_PAL_K

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_K1

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_L

Represents the PAL standard.


### -field D3DKMDT_VSS_PAL_M

Represents the PAL standard.


### -field D3DKMDT_VSS_OTHER

Represents any video standard other than those represented by the previous constants in this enumeration.


## -remarks
The <b>SignalInfo</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure is a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_signal_info.md">D3DKMDT_VIDEO_SIGNAL_MODE</a> structure.

The <b>VideoStandard</b> member of the D3DKMDT_VIDEO_SIGNAL_MODE structure is a D3DKMDT_VIDEO_SIGNAL_STANDARD value.


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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPn Target Mode Set Interface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

