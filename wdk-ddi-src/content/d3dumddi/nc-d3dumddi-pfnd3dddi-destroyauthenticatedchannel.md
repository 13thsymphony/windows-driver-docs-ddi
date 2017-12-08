---
UID: NC.d3dumddi.PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL
title: PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL
author: windows-driver-content
description: The DestroyAuthenticatedChannel function releases resources for the authenticated channel that the CreateAuthenticatedChannel function creates.
old-location: display\destroyauthenticatedchannel.htm
old-project: display
ms.assetid: ccea427b-e19e-433b-91b0-b40ce7c1da5a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyAuthenticatedChannel is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DestroyAuthenticatedChannel
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
req.iface: 
---

# PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL callback



## -description
<p>The <b>DestroyAuthenticatedChannel</b> function releases resources for the authenticated channel that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function creates. </p>


## -prototype

````
PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL DestroyAuthenticatedChannel;

__checkReturn HRESULT APIENTRY DestroyAuthenticatedChannel(
  _In_       HANDLE                                hDevice,
  _In_ const D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL *pData
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param pData [in]

<dd>
<p> A pointer to a <a href="display.d3dddiarg_destroyauthenticatedchannel">D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL</a> structure that contains one member that specifies the handle to the authenticated channel to destroy. </p>
</dd>
</dl>

## -returns
<p><b>DestroyAuthenticatedChannel</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The authenticated channel is successfully destroyed. </p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-destroyauthenticatedchannel.md">DestroyAuthenticatedChannel</a> could not allocate the required memory for it to complete.</p>

<p> </p>

## -remarks
<p>The driver's <b>DestroyAuthenticatedChannel</b> function should disable any protections that were set through calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function with the D3DAUTHETICATEDCONFIGURE_PROTECTION and D3DAUTHENTICATEDCONFIGURE_ENCRYPTIONWHENACCESIBLE GUIDs set. However, the driver should not disable shared surface protection (D3DAUTHETICATEDCONFIGURE_SHAREDRESOURCE).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p><i>DestroyAuthenticatedChannel</i> is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createauthenticatedchannel.md">CreateAuthenticatedChannel</a>
</dt>
<dt>
<a href="display.d3dddiarg_destroyauthenticatedchannel">D3DDDIARG_DESTROYAUTHENTICATEDCHANNEL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
