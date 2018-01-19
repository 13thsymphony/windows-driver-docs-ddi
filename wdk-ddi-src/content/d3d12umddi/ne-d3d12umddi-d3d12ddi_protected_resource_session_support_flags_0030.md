---
UID : NE:d3d12umddi.D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030
title : D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030
author : windows-driver-content
description : The protected resource session support flags.
old-location : display\d3d12ddi-protected-resource-session-support-flags-0030.htm
old-project : display
ms.assetid : f313ee29-9ff4-415b-9a0e-900bf751bb88
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030, D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030
req.alt-loc : d3d12umddi.h
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
req.typenames : D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030
---

# D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030 Enumeration
The protected resource session support flags.

## Syntax
````
typedef enum _D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030 { 
  D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAG_0030_NONE,
  D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAG_0030_SUPPORTED
} D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030;
````

## Constants

<table>

<tr>
<td>D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAG_0030_NONE</td>
<td>There are no  protected resource session support flags.</td>
</tr>

<tr>
<td>D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAG_0030_SUPPORTED</td>
<td>The protected resource session support flag is supported.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h |