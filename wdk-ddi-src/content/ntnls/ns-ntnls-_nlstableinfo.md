---
UID: NS.NTNLS._NLSTABLEINFO
title: _NLSTABLEINFO
author: windows-driver-content
description: Stores the NLS file formats .
old-location: kernel\nlstableinfo.htm
old-project: kernel
ms.assetid: B9E64163-B338-49C9-8167-C36B110AB710
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _NLSTABLEINFO, *PNLSTABLEINFO, NLSTABLEINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntnls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NLSTABLEINFO
req.alt-loc: Ntnls.h
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

# _NLSTABLEINFO structure



## -description
Stores the NLS file formats .



## -syntax

````
typedef struct _NLSTABLEINFO {
  CPTABLEINFO    OemTableInfo;
  CPTABLEINFO    AnsiTableInfo;
  PUSHORT        UpperCaseTable;
  LowerCaseTable PUSHORT;
} NLSTABLEINFO, *PNLSTABLEINFO;
````


## -struct-fields

### -field OemTableInfo

Specifies OEM table.


### -field AnsiTableInfo

Specifies an ANSI table. 


### -field UpperCaseTable

Specifies an 844 format uppercase table.


### -field PUSHORT

Specifies an 844 format lowercase table.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntnls.h</dt>
</dl>
</td>
</tr>
</table>