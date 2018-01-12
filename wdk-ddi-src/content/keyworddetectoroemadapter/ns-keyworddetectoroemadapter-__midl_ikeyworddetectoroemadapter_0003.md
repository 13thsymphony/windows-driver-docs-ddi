---
UID: NS:keyworddetectoroemadapter.__MIDL_IKeywordDetectorOemAdapter_0003
title: __MIDL_IKeywordDetectorOemAdapter_0003
author: windows-driver-content
description: The KEYWORDSELECTOR struct is a triplet of IDs that uniquely select a particular keyword, language, and user combination.
old-location: audio\keywordselector.htm
old-project: audio
ms.assetid: 762A7E36-E0F8-475C-B201-217D8FD8EBD6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: __MIDL_IKeywordDetectorOemAdapter_0003, KEYWORDSELECTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: keyworddetectoroemadapter.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEYWORDSELECTOR
req.alt-loc: KeywordDetectorOemAdapter.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: KeywordDetectorOemAdapter.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: KEYWORDSELECTOR
---

# __MIDL_IKeywordDetectorOemAdapter_0003 structure



## -description
The <b>KEYWORDSELECTOR</b> struct is a triplet of IDs that uniquely select a particular keyword, language, and user combination.



## -syntax

````
typedef struct {
  KEYWORDID KeywordId;
  LANGID    LangId;
} KEYWORDSELECTOR;
````


## -struct-fields

### -field KeywordId

Identifies a keyword function.


### -field LangId

Identifies a language.


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
<dt>KeywordDetectorOemAdapter.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IDL

</th>
<td width="70%">
<dl>
<dt>KeywordDetectorOemAdapter.idl</dt>
</dl>
</td>
</tr>
</table>