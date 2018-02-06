---
UID: NE:d3dkmdt._D3DKMDT_VIDEO_SIGNAL_STANDARD
title: "_D3DKMDT_VIDEO_SIGNAL_STANDARD"
author: windows-driver-content
description: The D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration contains constants that represent video signal standards.
old-location: display\d3dkmdt_video_signal_standard.htm
old-project: display
ms.assetid: bb129e02-ae01-4bbc-a81f-809f1a27060c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/D3DKMDT_VSS_EIA_861, d3dkmdt/D3DKMDT_VSS_PAL_L, D3DKMDT_VSS_NTSC_443, D3DKMDT_VSS_EIA_861, d3dkmdt/D3DKMDT_VSS_UNINITIALIZED, D3DKMDT_VIDEO_SIGNAL_STANDARD, d3dkmdt/D3DKMDT_VSS_VESA_DMT, D3DKMDT_VSS_NTSC_J, D3DKMDT_VSS_PAL_I, d3dkmdt/D3DKMDT_VSS_SECAM_B, D3DKMDT_VSS_SECAM_K, d3dkmdt/D3DKMDT_VSS_PAL_N, D3DKMDT_VSS_PAL_K, d3dkmdt/D3DKMDT_VSS_SECAM_K1, _D3DKMDT_VIDEO_SIGNAL_STANDARD, D3DKMDT_VSS_PAL_L, d3dkmdt/D3DKMDT_VSS_PAL_H, D3DKMDT_VSS_IBM, D3DKMDT_VSS_SECAM_H, d3dkmdt/D3DKMDT_VSS_SECAM_H, d3dkmdt/D3DKMDT_VSS_PAL_G, D3DKMDT_VSS_EIA_861A, d3dkmdt/D3DKMDT_VSS_SECAM_G, D3DKMDT_VSS_UNINITIALIZED, D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration [Display Devices], d3dkmdt/D3DKMDT_VSS_EIA_861A, D3DKMDT_VSS_EIA_861B, D3DKMDT_VSS_PAL_M, D3DKMDT_VSS_PAL_H, d3dkmdt/D3DKMDT_VSS_OTHER, d3dkmdt/D3DKMDT_VSS_EIA_861B, D3DKMDT_VSS_PAL_D, D3DKMDT_VSS_SECAM_B, D3DKMDT_VSS_VESA_DMT, d3dkmdt/D3DKMDT_VSS_VESA_GTF, D3DKMDT_VSS_SECAM_D, DmEnums_8174e59a-c264-4642-b770-d4e38236a6b7.xml, d3dkmdt/D3DKMDT_VIDEO_SIGNAL_STANDARD, D3DKMDT_VSS_PAL_N, d3dkmdt/D3DKMDT_VSS_PAL_B, d3dkmdt/D3DKMDT_VSS_IBM, D3DKMDT_VSS_VESA_GTF, d3dkmdt/D3DKMDT_VSS_PAL_D, d3dkmdt/D3DKMDT_VSS_NTSC_M, D3DKMDT_VSS_OTHER, D3DKMDT_VSS_PAL_B1, D3DKMDT_VSS_PAL_G, d3dkmdt/D3DKMDT_VSS_SECAM_D, D3DKMDT_VSS_NTSC_M, D3DKMDT_VSS_SECAM_L1, d3dkmdt/D3DKMDT_VSS_PAL_M, D3DKMDT_VSS_PAL_NC, d3dkmdt/D3DKMDT_VSS_NTSC_443, D3DKMDT_VSS_SECAM_K1, d3dkmdt/D3DKMDT_VSS_PAL_K, D3DKMDT_VSS_PAL_K1, D3DKMDT_VSS_APPLE, d3dkmdt/D3DKMDT_VSS_VESA_CVT, d3dkmdt/D3DKMDT_VSS_PAL_I, d3dkmdt/D3DKMDT_VSS_PAL_B1, d3dkmdt/D3DKMDT_VSS_PAL_K1, display.d3dkmdt_video_signal_standard, d3dkmdt/D3DKMDT_VSS_APPLE, d3dkmdt/D3DKMDT_VSS_SECAM_L, d3dkmdt/D3DKMDT_VSS_SECAM_L1, d3dkmdt/D3DKMDT_VSS_SECAM_K, D3DKMDT_VSS_SECAM_G, d3dkmdt/D3DKMDT_VSS_PAL_NC, D3DKMDT_VSS_VESA_CVT, D3DKMDT_VSS_SECAM_L, D3DKMDT_VSS_PAL_B, d3dkmdt/D3DKMDT_VSS_NTSC_J
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_VIDEO_SIGNAL_STANDARD
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDEO_SIGNAL_STANDARD
---

# _D3DKMDT_VIDEO_SIGNAL_STANDARD Enumeration
The D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration contains constants that represent video signal standards.

## Syntax
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

## Constants

<table>
            
                <tr>
                    <td>D3DKMDT_VSS_APPLE</td>
                    <td>Represents the Apple standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_EIA_861</td>
                    <td>Represents the Electronics Industries Association (EIA) standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_EIA_861A</td>
                    <td>Represents the EIA standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_EIA_861B</td>
                    <td>Represents the EIA standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_IBM</td>
                    <td>Represents the IBM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_NTSC_443</td>
                    <td>Represents the NTSC standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_NTSC_J</td>
                    <td>Represents the NTSC standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_NTSC_M</td>
                    <td>Represents the National Television Standards Committee (NTSC) standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_OTHER</td>
                    <td>Represents any video standard other than those represented by the previous constants in this enumeration.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_B</td>
                    <td>Represents the Phase Alteration Line (PAL) standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_B1</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_D</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_G</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_H</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_I</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_K</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_K1</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_L</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_M</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_N</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_PAL_NC</td>
                    <td>Represents the PAL standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_B</td>
                    <td>Represents the Systeme Electronic Pour Couleur Avec Memoire (SECAM) standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_D</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_G</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_H</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_K</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_K1</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_L</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_SECAM_L1</td>
                    <td>Represents the SECAM standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_UNINITIALIZED</td>
                    <td>Indicates that a variable of type D3DKMDT_VIDEO_SIGNAL_STANDARD has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_VESA_CVT</td>
                    <td>Represents the VESA Coordinated Video Timing (CVT) standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_VESA_DMT</td>
                    <td>Represents the Video Electronics Standards Association (VESA) Display Monitor Timing (DMT) standard.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_VSS_VESA_GTF</td>
                    <td>Represents the VESA Generalized Timing Formula (GTF) standard.</td>
                </tr>
</table>

    ## Remarks

        The <b>SignalInfo</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_target_mode.md">D3DKMDT_VIDPN_TARGET_MODE</a> structure is a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_video_signal_info.md">D3DKMDT_VIDEO_SIGNAL_MODE</a> structure.

The <b>VideoStandard</b> member of the D3DKMDT_VIDEO_SIGNAL_MODE structure is a D3DKMDT_VIDEO_SIGNAL_STANDARD value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

    ## See Also

        <a href="https://msdn.microsoft.com/library/windows/hardware/ff570559">VidPn Target Mode Set Interface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_SIGNAL_STANDARD enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>