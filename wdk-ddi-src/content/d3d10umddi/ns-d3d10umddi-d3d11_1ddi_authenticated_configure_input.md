---
UID : NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
title : D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
author : windows-driver-content
description : Contains input data for the ConfigureAuthenticatedChannel(D3D11_1) function.
old-location : display\d3d11_1ddi_authenticated_configure_input.htm
old-project : display
ms.assetid : a481fb2d-60bb-441d-998d-acb983b2c0ed
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
req.alt-loc : D3d10umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT structure
Contains input data for the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.

## Syntax
````
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT {
  D3D11_1DDI_OMAC omac;
  GUID            ConfigureType;
  HANDLE          hChannel;
  UINT            SequenceNumber;
} D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT;
````

## Members

        
            `ConfigureType`

            A GUID that specifies the command. The following GUIDs are defined.
        
            `hChannel`

            A handle to the authenticated channel. This handle was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.
        
            `omac`

            A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_omac.md">D3D11_1DDI_OMAC</a> structure that contains a Message Authentication Code (MAC) of the data. The driver uses Advanced Encryption Standard (AES)-based one-key CBC MAC (OMAC) to calculate this value for the block of data that appears after this structure member.
        
            `SequenceNumber`

            The query sequence number.

<div class="alert"><b>Note</b>  The sequence number must increase with each successive call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.</div>
<div> </div>

    ## Remarks
        For information on the usage of this structure, see the Remarks of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_omac.md">D3D11_1DDI_OMAC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>