---
UID: NS.D3DUKMDT._D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
title: _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
author: windows-driver-content
description: D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE specifies the protection on the graphics processing unit (GPU) virtual address that is mapped.
old-location: display\d3dddigpuvirtualaddress_protection_type.htm
old-project: display
ms.assetid: CA46EEC4-5F3D-4E4C-8C83-6D91BE301C68
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE, D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
req.alt-loc: d3dukmdt.h
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

# _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE structure



## -description
<b>D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE</b> specifies the protection on the graphics processing unit (GPU) virtual address that is mapped.



## -syntax

````
typedef struct _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE {
  union {
    struct {
      UINT64 Write  :1;
      UINT64 Execute  :1;
      UINT64 Zero  :1;
      UINT64 NoAccess  :1;
      UINT64 SystemUseOnly  :1;
      UINT64 Reserved  :59;
    };
    UINT64 Value;
  };
} D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE;
````


## -struct-fields

### -field Write

The pages will be allowed read-write access.


### -field Execute

The pages will be allowed execute access.


### -field Zero

The pages will be put to the <i>zero</i> state.


### -field NoAccess

The pages will be put to the <i>invalid</i> state.


### -field SystemUseOnly

This member is for system use only and should not be set by the user mode driver.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

The consolidated value of the structure's members.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>