---
UID: NS.D3DUMDDI._D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL
title: _D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL
author: windows-driver-content
description: The D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure describes the state that is set within an authenticated channel by using the ConfigureAuthenticatedChannel function.
old-location: display\d3dddiarg_configureauthenticatedchannel.htm
old-project: display
ms.assetid: 8f27fe6d-fe34-4006-a8b1-d2f2190ec044
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL, D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL
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

# _D3DDDIARG_CONFIGUREAUTHENICATEDCHANNEL structure



## -description
The D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure describes the state that is set within an authenticated channel by using the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function. 


## -syntax

````
typedef struct _D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL {
  UINT       InputSize;
  const VOID *pInputData;
  VOID       *pOutputData;
} D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL;
````


## -struct-fields

### -field InputSize

[in] The size, in bytes, of the input data that the <b>pInputData</b> member points to. 

### -field pInputData

[in] A pointer to a buffer that describes the configuration data to set. The definition of the input buffer depends on the configuration data that is set. The buffer that <b>pInputData</b> points to is defined identically to the input buffer that is passed to the <b>IDirect3DAuthenticatedChannel::Configure</b> method. For more information about <b>IDirect3DAuthenticatedChannel::Configure</b>, see the Windows SDK documentation. 

### -field pOutputData

[in/out] A pointer to a buffer that describes the information that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function returns. 

## -remarks
The first member of the input buffer that the <b>pInputData</b> member points to is always the D3DAUTHENTICATEDCHANNEL_CONFIGURE_INPUT structure, whose members specify the following information: 

The <b>ConfigureType</b> member identifies the configuration state to set. 

The <b>omac</b> member identifies the One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC), which verifies that the input is from a trusted source.

The <b>SequenceNumber</b> member specifies a unique number that the driver can use to prevent against replay attacks. 

The <b>pOutputData</b> member points to a D3DAUTHENTICATEDCHANNEL_CONFIGURE_OUTPUT structure that contains the configuration type and the sequence number of the output buffer to prevent against replay attacks. 

Configuration state that an authenticated channel sets cannot be disabled by another authenticated channel. A call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> function with such an attempt   fails. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL is supported beginning with the Windows 7 operating system.
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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CONFIGUREAUTHENTICATEDCHANNEL structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
