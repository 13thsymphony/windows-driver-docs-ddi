---
UID: NE.bthhfpddi._HFP_BYPASS_CODEC_ID_VERSION
title: _HFP_BYPASS_CODEC_ID_VERSION
author: windows-driver-content
description: The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service.
old-location: audio\hfp_bypass_codec_id_version.htm
old-project: audio
ms.assetid: A16980CD-3F2F-4A67-902A-F3D72AA042D9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION, PHFP_BYPASS_CODEC_ID_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HFP_BYPASS_CODEC_ID_VERSION
req.alt-loc: Bthhfpddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
---

# _HFP_BYPASS_CODEC_ID_VERSION enumeration



## -description
The HFP_BYPASS_CODEC_ID_VERSION enumeration defines the codec ID structure versions that are supported by the HFP service.



## -syntax

````
typedef enum _HFP_BYPASS_CODEC_ID_VERSION { 
  REQ_HFP_BYPASS_CODEC_ID_V1  = 1
} HFP_BYPASS_CODEC_ID_VERSION;
````


## -enum-fields

### -field REQ_HFP_BYPASS_CODEC_ID_V1

Codec ID structure version 1.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthhfpddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_codec_id.md">IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</a>
</dt>
<dt>
<a href="audio.hfp_bypass_codec_id_v1">HFP_BYPASS_CODEC_ID_V1</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HFP_BYPASS_CODEC_ID_VERSION enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

