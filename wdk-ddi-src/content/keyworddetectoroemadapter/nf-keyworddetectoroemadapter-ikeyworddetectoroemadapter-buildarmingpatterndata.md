---
UID: NF.keyworddetectoroemadapter.IKeywordDetectorOemAdapter.BuildArmingPatternData
title: IKeywordDetectorOemAdapter::BuildArmingPatternData method
author: windows-driver-content
description: The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.
old-location: audio\ikeyworddetectoroemadapter_buildarmingpatterndata.htm
old-project: audio
ms.assetid: F74DC3C3-C182-4BBA-93C8-95A73C58CFEF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter::BuildArmingPatternData, BuildArmingPatternData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: keyworddetectoroemadapter.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKeywordDetectorOemAdapter.BuildArmingPatternData
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
---

# IKeywordDetectorOemAdapter::BuildArmingPatternData method



## -description
The <b>BuildArmingPatternData</b> method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.



## -syntax

````
HRESULT BuildArmingPatternData(
  [in]  IStream                     *ModelData,
  [in]  KEYWORDSELECTOR             *KeywordSelectors,
  [in]  ULONG                       NumKeywordSelectors,
  [out] SOUNDDETECTOR_PATTERNHEADER **ppPatternData = 0
);
````


## -parameters

### -param ModelData [in]

A pointer to <b>IStream</b> bound to model data for the <a href="audio.keywordselector">KEYWORDSELECTOR</a> values in the <i>KeywordSelectors</i> parameter.


### -param KeywordSelectors [in]

An array of <a href="audio.keywordselector">KEYWORDSELECTOR</a> structures identifying the desired set of matches for the keyword detector to arm.


### -param NumKeywordSelectors [in]

The number of items in the <i>KeywordSelectors</i> array. Only one key word selector is supported and this field must be set to one.


### -param ppPatternData [out]

The pattern data for the operating system to pass to the audio driver. The OEMDLL allocates the memory calling <a href="com.cotaskmemalloc">CoTaskMemAlloc</a>. The operating system will free the memory by calling <a href="com.cotaskmemfree">CoTaskMemFree</a>.


## -returns
This method can return one of these values.
<dl>
<dt>S_OK</dt>
</dl>The function exited successfully. 
<dl>
<dt>E_POINTER</dt>
</dl> The <i>ModelData</i> pointer is <b>NULL</b>.
<dl>
<dt>E_INVALIDARG</dt>
</dl> The <i>KeywordId</i> or <i>LangId</i> parameters are invalid.
<dl>
<dt>HRESULT_FROM_WIN32(ERROR_GEN_FAILURE)</dt>
</dl> The processing was unable to complete.

 


## -remarks
The operating system may call this method at any time. The operating system may also store the returned pattern data to reuse later for the same set of keyword selectors.


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

## -see-also
<dl>
<dt>
<a href="..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md">IKeywordDetectorOemAdapter</a>
</dt>
<dt>
<a href="audio.keywordselector">KEYWORDSELECTOR</a>
</dt>
<dt>
<a href="com.cotaskmemalloc">CoTaskMemAlloc</a>
</dt>
<dt>
<a href="com.cotaskmemfree">CoTaskMemFree</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::BuildArmingPatternData method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

