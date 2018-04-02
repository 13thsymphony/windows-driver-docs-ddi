---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
title: D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
author: windows-driver-content
description: Contains input data for a call to the ConfigureAuthenticatedChannel(D3D11_1) function when D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT.ConfigureType has a GUID value of D3D11_AUTHENTICATED_CONFIGURE_INITIALIZE.
old-location: display\d3d11_1ddi_authenticated_configure_initialize.htm
old-project: display
ms.assetid: 7a087c7b-3ce7-4054-9880-9940ce589fa4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE, D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure [Display Devices], D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE, D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE, display.d3d11_1ddi_authenticated_configure_initialize
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
-	D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE
---

# D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE structure
Contains input data for a call to the <a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a> function when <a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>.<b>ConfigureType</b> has a GUID value of <b>D3D11_AUTHENTICATED_CONFIGURE_INITIALIZE</b>.

## Syntax
```
typedef struct D3D11_1DDI_AUTHENTICATED_CONFIGURE_INITIALIZE {
  D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT Parameters;
  UINT                                     StartSequenceQuery;
  UINT                                     StartSequenceConfigure;
} D3D11_DDI_AUTHENTICATED_CONFIGURE_INITIALIZE;
```

## Members


`Parameters`

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a> structure that contains the command GUID and other data.

`StartSequenceQuery`

The initial sequence number for queries.

`StartSequenceConfigure`

The initial sequence number for commands.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/28d32813-15f5-4b9c-9bdb-5ad9b47bbe3b">ConfigureAuthenticatedChannel(D3D11_1)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406358">D3D11_1DDI_AUTHENTICATED_CONFIGURE_INPUT</a>