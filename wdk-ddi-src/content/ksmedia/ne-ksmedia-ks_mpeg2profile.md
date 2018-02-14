---
UID: NE:ksmedia.KS_MPEG2Profile
title: KS_MPEG2Profile
author: windows-driver-content
description: The KS_MPEG2Profile enumeration describes MPEG-2 profiles.
old-location: stream\ks_mpeg2profile.htm
old-project: stream
ms.assetid: 1846e6b7-5b98-4850-86d6-ef6a29ce050b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KS_MPEG2Profile_Main, ksmedia/KS_MPEG2Profile_Main, ksmedia/KS_MPEG2Profile_SpatiallyScalable, stream.ks_mpeg2profile, ksmedia/KS_MPEG2Profile_SNRScalable, KS_MPEG2Profile enumeration [Streaming Media Devices], ksmedia/KS_MPEG2Profile_High, KS_MPEG2Profile_Simple, KS_MPEG2Profile_High, vidcapstruct_25932d29-3acc-415e-a13f-f02298c12c1d.xml, KS_MPEG2Profile_SNRScalable, ksmedia/KS_MPEG2Profile, KS_MPEG2Profile, KS_MPEG2Profile_SpatiallyScalable, ksmedia/KS_MPEG2Profile_Simple
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_MPEG2Profile
product: Windows
targetos: Windows
req.typenames: KS_MPEG2Profile
---

# KS_MPEG2Profile Enumeration
The KS_MPEG2Profile enumeration describes MPEG-2 profiles.

## Syntax
````
typedef enum  { 
  KS_MPEG2Profile_Simple             = 0,
  KS_MPEG2Profile_Main               = 1,
  KS_MPEG2Profile_SNRScalable        = 2,
  KS_MPEG2Profile_SpatiallyScalable  = 3,
  KS_MPEG2Profile_High               = 4
} KS_MPEG2Profile;
````

## Constants

<table>
            
                <tr>
                    <td>KS_MPEG2Profile_High</td>
                    <td>Similar to <b>KS_MPEG2Profile_Main</b>, with spatial scalability, scalable signal-to-noise, and 4:2:2 macroblocks.</td>
                </tr>
            
                <tr>
                    <td>KS_MPEG2Profile_Main</td>
                    <td>Specifies the main MPEG-2 profile, generally intended for cable or satellite television.</td>
                </tr>
            
                <tr>
                    <td>KS_MPEG2Profile_Simple</td>
                    <td>Specifies the simple MPEG-2 profile, generally intended for software applications and some cable television.</td>
                </tr>
            
                <tr>
                    <td>KS_MPEG2Profile_SNRScalable</td>
                    <td>Similar to <b>KS_MPEG2Profile_Main</b>, with scalable signal-to-noise.</td>
                </tr>
            
                <tr>
                    <td>KS_MPEG2Profile_SpatiallyScalable</td>
                    <td>Similar to <b>KS_MPEG2Profile_Main</b>, with spatial scalability.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

    ## See Also

        <a href="..\ksmedia\ns-ksmedia-tagks_mpegvideoinfo2.md">KS_MPEGVIDEOINFO2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_MPEG2Profile enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>