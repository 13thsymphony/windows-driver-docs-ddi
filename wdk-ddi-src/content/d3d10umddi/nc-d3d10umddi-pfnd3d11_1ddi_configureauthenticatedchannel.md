---
UID: NC:d3d10umddi.PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL
title: PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL
author: windows-driver-content
description: Processes a request from an application to configure an authenticated channel for content protection. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.
old-location: display\configureauthenticatedchannel1.htm
old-project: display
ms.assetid: 28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.configureauthenticatedchannel1, ConfigureAuthenticatedChannel callback function [Display Devices], ConfigureAuthenticatedChannel, PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL, PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL, d3d10umddi/ConfigureAuthenticatedChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	ConfigureAuthenticatedChannel
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL callback function
Processes  a request from an application to configure an authenticated channel for content protection. Implemented by a Windows Display Driver Model (WDDM) 1.2 or later user-mode display driver.

## Syntax

```
PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL Pfnd3d111DdiConfigureauthenticatedchannel;

HRESULT Pfnd3d111DdiConfigureauthenticatedchannel(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HAUTHCHANNEL hCAuthChannel,
  UINT InputDataSize,
  CONST VOID *pInputData,
  D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT *pOutputData
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hCAuthChannel`

A handle to the authenticated channel object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.

`InputDataSize`

The size, in bytes, of the array that is specified by the <i>pInputData</i> parameter.

`*pInputData`

A pointer to a byte array that contains input data for the command. For more information, see the Remarks section.

`*pOutputData`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a> structure. For more information, see the Remarks section.


## Return Value

Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The authenticated channel was configured successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support the specified command

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>

## Remarks

The byte array that is referenced by the <i>pInputData</i> parameter is formatted in the following way:

<ul>
<li>
This array starts with a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure. 

</li>
<li>
The data that follows this structure is in a format that is specified by the <b>ConfigureType</b> member of the structure. The following list describes the format of this data based on the <b>ConfigureType</b> member. 

<dl>
<dt><a id="D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID"></a><a id="d3d11_1ddi_authenticated_configure_crypto_session_guid"></a><b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION_GUID</b></dt>
<dd>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_crypto_session.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_CRYPTO_SESSION</a>


</dd>
<dt><a id="D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID"></a><a id="d3d11_1ddi_authenticated_configure_encryption_when_accessible_guid"></a><b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_ENCRYPTION_WHEN_ACCESSIBLE_GUID</b></dt>
<dd>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_accessible_encryption.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_ACCESSIBLE_ENCRYPTION</a>


</dd>
<dt><a id="D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID"></a><a id="d3d11_1ddi_authenticated_configure_initialize_guid"></a><b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE_GUID</b></dt>
<dd>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_initialize.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE</a>


</dd>
<dt><a id="D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID"></a><a id="d3d11_1ddi_authenticated_configure_protection_guid"></a><b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION_GUID</b></dt>
<dd>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_protection.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_PROTECTION</a>


</dd>
<dt><a id="D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID"></a><a id="d3d11_1ddi_authenticated_configure_shared_resource_guid"></a><b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE_GUID</b></dt>
<dd>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_shared_resource.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</a>


</dd>
</dl>


</li>
</ul>
The <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure contains an AES-based one-key CBC message authentication code (OMAC) of the data. The display miniport driver must calculate its own OMAC over the data to authenticate the data. This input structure also contains a driver handle to the authenticated channel, a sequence number, and a GUID that indicates the configuration type.



The display miniport driver follows these steps when it initializes the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a> structure:

<ol>
<li>
The driver must copy the input data to the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a> structure.

</li>
<li>
The driver must set the  <b>ReturnCode</b> member to the same return code that it will return for the <i>ConfigureAuthenticatedChannel(D3D11_1)</i> call. This provides the application with a secure mechanism of accessing the return code. 



</li>
<li>
The driver sets the <b>omac</b> member to zero and then calculates an OMAC for the data in the structure. The driver then sets the <b>omac</b> member to the OMAC that it calculated.

</li>
</ol>
The display miniport driver must return  <b>E_INVALIDARG</b> for the <b>ConfigureAuthenticatedChannel</b> call under the following conditions:

<ul>
<li>
The <b>omac</b> member of the  <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure does not match the OMAC that the driver calculated.

</li>
<li>
The sequence number is not greater than a sequence number that was specified in a previous configuration call.

</li>
<li>
The sequence number has not yet been initialized by a call  to the <i>ConfigureAuthenticatedChannel(D3D11_1)</i> function.



</li>
<li>
The <i>InputDataSize</i> parameter is less than the size of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure plus the size of the structure specified by the  <b>D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType</b> member.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_output.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_OUTPUT</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CONFIGUREAUTHENTICATEDCHANNEL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>