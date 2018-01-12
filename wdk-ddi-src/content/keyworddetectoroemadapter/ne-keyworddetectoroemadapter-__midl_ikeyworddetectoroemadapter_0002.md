---
UID: NE:keyworddetectoroemadapter.__MIDL_IKeywordDetectorOemAdapter_0002
title: __MIDL_IKeywordDetectorOemAdapter_0002
author: windows-driver-content
description: The KEYWORDID enumeration identifies the phrase text/function of a keyword. The value is also be used in the Windows Biometric Service adapters.
old-location: audio\keywordid.htm
old-project: audio
ms.assetid: 88D85EB1-11BC-42B9-B22E-5FB58F409C75
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: __MIDL_IKeywordDetectorOemAdapter_0002, KEYWORDID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: keyworddetectoroemadapter.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEYWORDID
req.alt-loc: KeywordDetectorOemAdapter.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: KeywordDetectorOemAdapter.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
req.typenames: KEYWORDID
---

# __MIDL_IKeywordDetectorOemAdapter_0002 enumeration



## -description
The <b>KEYWORDID</b> enumeration identifies the phrase text/function of a keyword. The value is also be used in the Windows Biometric Service adapters.



## -syntax

````
typedef enum  { 
  KwInvalid                 = 0,
   KwVoiceAssistant         = 1,
        KwSelection         = 2
} KEYWORDID;
````


## -enum-fields

### -field KwInvalid      

Indicates that the keyword was invalid.


### -field  KwVoiceAssistant

Indicates that the "hey Cortana" keyword was used.


### -field       KwSelection       

Indicates the "select" keyword was used.


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