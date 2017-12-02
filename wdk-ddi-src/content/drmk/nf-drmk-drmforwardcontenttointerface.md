---
UID: NF.drmk.DrmForwardContentToInterface
title: DrmForwardContentToInterface
author: windows-driver-content
description: The DrmForwardContentToInterface function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content.
old-location: audio\drmforwardcontenttointerface.htm
old-project: audio
ms.assetid: 13326eae-3160-42e5-9254-089c8cdc97a3
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: DrmForwardContentToInterface
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
req.alt-api: DrmForwardContentToInterface
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
req.iface: 
---

# DrmForwardContentToInterface function



## -description
<p>The <code>DrmForwardContentToInterface</code> function accepts a pointer to the COM interface of an object to which the caller intends to forward protected content. The function authenticates the object and sends the object the content ID and DRM rights that the system has assigned to the protected content.</p>


## -syntax

````
NTSTATUS DrmForwardContentToInterface(
  _In_ ULONG    ContentId,
  _In_ PUNKNOWN pUnknown,
  _In_ ULONG    NumMethods
);
````


## -parameters
<dl>

### -param ContentId [in]

<dd>
<p>Specifies the DRM content ID. This parameter identifies a protected KS audio stream.</p>
</dd>

### -param pUnknown [in]

<dd>
<p>Pointer to a COM interface that directly receives KS audio stream data for a KS audio filter.</p>
</dd>

### -param NumMethods [in]

<dd>
<p>Specifies the total number of methods in the COM interface that <i>pUnknown</i> points to, including all the methods in its base interfaces.</p>
</dd>
</dl>

## -returns
<p><code>DrmForwardContentToInterface</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code. The following table shows some of the possible return status codes.</p><dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl><p>Indicates that the KS audio stream that is associated with <i>pUnknown</i> does not support the DRM content rights that are assigned to <i>ContentId</i>.</p>

<p> </p>

## -remarks
<p>Before allowing protected content to flow through a data path, the system verifies that the data path is secure. To do so, the system authenticates each module in the data path beginning at the upstream end of the data path and moving downstream. As each module is authenticated, that module gives the system information about the next module in the data path so that it can also be authenticated. To be successfully authenticated, a module's binary file must be signed as DRM-compliant.</p>

<p>If two adjacent modules in the data path communicate with each other through the downstream module's COM interface, the upstream module calls the <code>DrmForwardContentToInterface</code> function to provide the system with a pointer to the COM interface. (If the two modules communicate through the <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a> function or the downstream module's content handlers, the upstream module calls <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> or <a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a> instead.)</p>

<p><code>DrmForwardContentToInterface</code> authenticates the module that implements the methods in the COM interface pointed to by <i>pUnknown</i>. (If the methods are distributed among several modules, the function authenticates all these modules.) This vendor-defined interface must be understood by both the module that calls the interface and the module that implements the interface. <code>DrmForwardContentToInterface</code> makes no assumptions regarding this interface other than that it is derived from <b>IUnknown</b>.</p>

<p>If <code>DrmForwardContentToInterface</code> succeeds in authenticating the driver or library, it does the following:</p>

<p>Queries the <i>pUnknown</i> interface for its <a href="..\drmk\nn-drmk-idrmaudiostream.md">IDrmAudioStream</a> interface. Note that although the <code>DrmForwardContentToInterface</code> authenticates all the methods in the <i>pUnknown</i> interface, it does not call any methods in the <i>pUnknown</i> interface other than the base <b>IUnknown</b> methods.</p>

<p>Calls <a href="audio.idrmaudiostream_setcontentid">IDrmAudioStream::SetContentId</a> to set the DRM content ID and DRM content rights on the audio stream. Before returning, <code>DrmForwardContentToInterface</code> releases the <b>IDrmAudioStream</b> interface.</p>

<p>The <i>pUnknown</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.</p>

<p><code>DrmForwardContentToInterface</code> performs the same function as <a href="..\portcls\nf-portcls-pcforwardcontenttointerface.md">PcForwardContentToInterface</a> and <a href="audio.idrmport_forwardcontenttointerface">IDrmPort::ForwardContentToInterface</a>. For more information, see <a href="https://msdn.microsoft.com/62c739da-91e8-428e-b76c-ec9621b12597">DRM Functions and Interfaces</a>.</p>

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
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Drmk.lib</dt>
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
<a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmaddcontenthandlers.md">DrmAddContentHandlers</a>
</dt>
<dt>
<a href="..\drmk\nn-drmk-idrmaudiostream.md">IDrmAudioStream</a>
</dt>
<dt>
<a href="audio.idrmaudiostream_setcontentid">IDrmAudioStream::SetContentId</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcforwardcontenttointerface.md">PcForwardContentToInterface</a>
</dt>
<dt>
<a href="audio.idrmport_forwardcontenttointerface">IDrmPort::ForwardContentToInterface</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DrmForwardContentToInterface function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
