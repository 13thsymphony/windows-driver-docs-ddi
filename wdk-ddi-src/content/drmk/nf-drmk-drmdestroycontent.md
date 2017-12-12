---
UID: NF.drmk.DrmDestroyContent
title: DrmDestroyContent function
author: windows-driver-content
description: The DrmDestroyContent function deletes a DRM content ID that was created by DrmCreateContentMixed.
old-location: audio\drmdestroycontent.htm
old-project: audio
ms.assetid: 197f74f8-050e-4b0b-a95d-f640c565c17e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DrmDestroyContent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrmDestroyContent
req.alt-loc: Drmk.lib,Drmk.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Drmk.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DrmDestroyContent function



## -description
The <code>DrmDestroyContent</code> function deletes a DRM content ID that was created by <a href="audio.drmcreatecontentmixed">DrmCreateContentMixed</a>.



## -syntax

````
NTSTATUS DrmDestroyContent(
  _In_ ULONG ContentId
);
````


## -parameters

### -param ContentId [in]

Specifies a nonzero DRM content ID assigned to a KS audio stream by <b>DrmCreateContentMixed</b>. Note that a content ID of zero represents an audio stream with default DRM content rights, and cannot be used with this function.


## -returns
<b>DrmCreateContentMixed</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
A KS audio filter can only use <code>DrmDestroyContent</code> to delete a DRM content ID that it obtained by calling <a href="audio.drmcreatecontentmixed">DrmCreateContentMixed</a>. Note that a KS audio filter must not use <code>DrmDestroyContent</code> to delete a DRM content ID set by <a href="audio.idrmaudiostream_setcontentid">IDrmAudioStream::SetContentId</a> or by an IOCTL_KS_PROPERTY request that sets the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a> property. Only the KS audio filter that created the content ID should delete it.

<code>DrmDestroyContent</code> performs the same function as <a href="audio.pcdestroycontent">PcDestroyContent</a> and <a href="audio.idrmport_destroycontent">IDrmPort::DestroyContent</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Drmk.h (include Drmk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Drmk.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.drmcreatecontentmixed">DrmCreateContentMixed</a>
</dt>
<dt>
<a href="audio.drmgetcontentrights">DrmGetContentRights</a>
</dt>
<dt>
<a href="audio.idrmaudiostream_setcontentid">IDrmAudioStream::SetContentId</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
</dt>
<dt>
<a href="audio.pcdestroycontent">PcDestroyContent</a>
</dt>
<dt>
<a href="audio.idrmport_destroycontent">IDrmPort::DestroyContent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DrmDestroyContent function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

