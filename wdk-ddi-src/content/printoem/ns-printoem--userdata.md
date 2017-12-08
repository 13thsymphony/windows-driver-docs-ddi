---
UID: NS.printoem._USERDATA
title: USERDATA
author: windows-driver-content
description: The USERDATA structure is used by Unidrv and Pscript to specify additional information about printer features. A USERDATA structure pointer is supplied as the UserData member for each OPTITEM structure.
old-location: print\userdata.htm
old-project: print
ms.assetid: 5d4e5454-f44f-483a-a389-c8973263fbaa
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: USERDATA, USERDATA, *PUSERDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USERDATA
req.alt-loc: printoem.h
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
req.iface: IPrintSchemaTicket2
req.product: Windows 10 or later.
---

# USERDATA structure



## -description
<p>The USERDATA structure is used by <a href="wdkgloss.u#wdkgloss.unidrv#wdkgloss.unidrv"><i>Unidrv</i></a> and <a href="wdkgloss.p#wdkgloss.pscript#wdkgloss.pscript"><i>Pscript</i></a> to specify additional information about printer features. A USERDATA structure pointer is supplied as the <b>UserData</b> member for each <a href="..\compstui\ns-compstui--optitem.md">OPTITEM</a> structure.</p>


## -syntax

````
typedef struct _USERDATA {
  DWORD     dwSize;
  ULONG_PTR dwItemID;
  PSTR      pKeyWordName;
  DWORD     dwReserved[8];
} USERDATA, *PUSERDATA;
````


## -struct-fields
<dl>

### -field dwSize

<dd>
<p>Size, in bytes, of the USERDATA structure.</p>
</dd>

### -field dwItemID

<dd>
<p>Printer feature identifier.</p>
</dd>

### -field pKeyWordName

<dd>
<p>Pointer to a nonlocalized text string identifying a printer feature.</p>
</dd>

### -field dwReserved

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>