---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE.
old-location: display\d3d11_1ddi_authenticated_configure_shared_resource.htm
old-project: display
ms.assetid: 004046d1-552e-43a5-94b1-30b113e8b40e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE, D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE, display.d3d11_1ddi_authenticated_configure_shared_resource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE structure
Contains input data for a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE</b>.

## Syntax
````
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE {
  D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT         Parameters;
  D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE ProcessType;
  HANDLE                                           ProcessHandle;
  BOOL                                             AllowAccess;
} D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE;
````

## Members


`AllowAccess`

If <b>TRUE</b>, the specified process has access to restricted shared resources.

`Parameters`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data.

`ProcessHandle`

A process handle. If the <b>ProcessType</b> member equals <b>D3D11_1DDI_PROCESSIDTYPE_HANDLE</b>, the <b>ProcessHandle</b> member specifies a handle to a process. Otherwise, the value is ignored.

`ProcessType`

A <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_authenticated_process_identifier_type.md">D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE</a> value that specifies the type of process. To specify the DWM process, set this member to <b>D3D11_1DDI_PROCESSIDTYPE_DWM</b>. Otherwise, set this member to <b>D3D11_1DDI_PROCESSIDTYPE_HANDLE</b> and set the <b>ProcessHandle</b> member to a valid handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_authenticated_process_identifier_type.md">D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_configureauthenticatedchannel.md">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_configure_input.md">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_CONFIGURE_SHARED_RESOURCE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>