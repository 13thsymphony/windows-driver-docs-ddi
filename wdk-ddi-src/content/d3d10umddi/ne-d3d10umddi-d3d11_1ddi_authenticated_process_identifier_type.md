---
UID: NE:d3d10umddi.D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE
title: D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE
author: windows-driver-content
description: Specifies the type of process that is identified in the D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT structure.
old-location: display\d3d11_1ddi_authenticated_process_identifier_type.htm
old-project: display
ms.assetid: 7a8e7641-c946-4feb-b6d7-54ef63de9e76
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE, D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE
req.alt-loc: D3d10umddi.h
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
req.typenames: D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE
---

# D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE enumeration



## -description
Specifies the type of process that is identified in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_restricted_shared_resource_process_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT</a>  structure.



## -syntax

````
typedef enum D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE { 
  D3D11_1DDI_PROCESSIDTYPE_UNKNOWN  = 0,
  D3D11_1DDI_PROCESSIDTYPE_DWM      = 1,
  D3D11_1DDI_PROCESSIDTYPE_HANDLE   = 2
} D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE;
````


## -enum-fields

### -field D3D11_1DDI_PROCESSIDTYPE_UNKNOWN

Unknown process type.


### -field D3D11_1DDI_PROCESSIDTYPE_DWM

DWM process.


### -field D3D11_1DDI_PROCESSIDTYPE_HANDLE

Handle to a process.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_authenticated_query_restricted_shared_resource_process_output.md">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_PROCESS_IDENTIFIER_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

