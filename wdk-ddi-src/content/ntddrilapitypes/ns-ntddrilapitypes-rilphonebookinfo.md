---
UID: NS.NTDDRILAPITYPES.RILPHONEBOOKINFO
title: RILPHONEBOOKINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookinfo.htm
old-project: NetVista
ms.assetid: 626bfc9b-6d84-4b8c-89eb-c635d0cb61f0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILPHONEBOOKINFO, LPRILPHONEBOOKINFO, *LPRILPHONEBOOKINFO, RILPHONEBOOKINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILPHONEBOOKINFO
req.alt-loc: ntddrilapitypes.h
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

# RILPHONEBOOKINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILPHONEBOOKINFO {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwUsed;
  DWORD  dwTotal;
  DWORD  dwMaxAddressLength;
  DWORD  dwMaxTextLength;
  DWORD  dwMaxAdditionalNumbers;
  DWORD  dwMaxAdditionalNumberLength;
  DWORD  dwMaxAdditionalNumberTextLength;
  DWORD  dwUsedAdditionalNumberStrings;
  DWORD  dwTotalAdditionalNumberStrings;
  DWORD  dwMaxEmails;
  DWORD  dwMaxEmailAddressLength;
  DWORD  dwMaxGroups;
  DWORD  dwMaxGroupStringLength;
  DWORD  dwUsedGroupStrings;
  DWORD  dwTotalGroupStrings;
  DWORD  dwMaxSecondNameStringLength;
} RILPHONEBOOKINFO, RILPHONEBOOKINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwUsed


### -field dwTotal


### -field dwMaxAddressLength


### -field dwMaxTextLength


### -field dwMaxAdditionalNumbers


### -field dwMaxAdditionalNumberLength


### -field dwMaxAdditionalNumberTextLength


### -field dwUsedAdditionalNumberStrings


### -field dwTotalAdditionalNumberStrings


### -field dwMaxEmails


### -field dwMaxEmailAddressLength


### -field dwMaxGroups


### -field dwMaxGroupStringLength


### -field dwUsedGroupStrings


### -field dwTotalGroupStrings


### -field dwMaxSecondNameStringLength


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>