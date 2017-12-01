---
UID: NF.drmk.IDrmAudioStream.SetContentId
title: IDrmAudioStream::SetContentId
author: windows-driver-content
description: The SetContentId method sets the DRM content ID and its assigned DRM content rights on a KS audio stream.
old-location: audio\idrmaudiostream_setcontentid.htm
old-project: audio
ms.assetid: 0e9d13e8-c351-4730-8f00-6c149f824af0
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IDrmAudioStream, SetContentId, IDrmAudioStream::SetContentId
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
req.alt-api: IDrmAudioStream.SetContentId
req.alt-loc: drmk.h
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
req.iface: IDrmAudioStream
---

# IDrmAudioStream::SetContentId method



## -description
<p>The <code>SetContentId</code> method sets the DRM content ID and its assigned DRM content rights on a KS audio stream.</p>


## -syntax

````
NTSTATUS SetContentId(
  [in] ULONG       ContentId,
  [in] PCDRMRIGHTS DrmRights
);
````


## -parameters
<dl>

### -param <i>ContentId</i> [in]

<dd>
<p>Specifies the DRM content ID. This parameter is an identifier that the DRM system generates at run time to identify DRM-protected content in this stream.</p>
</dd>

### -param <i>DrmRights</i> [in]

<dd>
<p>Pointer to a <a href="audio.drmrights">DRMRIGHTS</a> structure specifying the rights granted by the content provider to the user for playing and copying DRM-protected content in this stream.</p>
</dd>
</dl>

## -returns
<p><code>SetContentId</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. If the filter cannot enforce the specified content rights, the method returns STATUS_NOT_IMPLEMENTED.</p>

## -remarks
<p>The DRM system can call the <code>SetContentId</code> method at any time during the lifetime of a KS audio stream.</p>

<p>A KS audio filter completes the execution of a call to the <code>SetContentId</code> method synchronously. If the function returns STATUS_SUCCESS, this indicates that all the downstream KS audio nodes (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536219">Audio Topology Nodes</a>) of a KS audio stream have also been successfully configured with the specified DRM content ID and DRM content rights. (The term <i>downstream node</i> refers to either a direct or an indirect sink for an audio stream.)</p>

<p>If the KS audio filter cannot enforce the specified DRM content rights, the <code>SetContentId</code> method returns the error code STATUS_NOT_IMPLEMENTED. In this case, the KS audio stream's previously set DRM content ID and DRM content rights remain set on the stream.</p>

<p>For more information about using this method, see <a href="NULL">Digital Rights Management</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Drmk.h (include Drmk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\drmk\nn-drmk-idrmaudiostream.md">IDrmAudioStream</a>
</dt>
<dt>
<a href="audio.drmrights">DRMRIGHTS</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IDrmAudioStream::SetContentId method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
