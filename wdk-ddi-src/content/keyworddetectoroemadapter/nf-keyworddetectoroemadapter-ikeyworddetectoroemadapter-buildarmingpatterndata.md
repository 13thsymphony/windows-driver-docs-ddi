---
UID : NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.BuildArmingPatternData
title : IKeywordDetectorOemAdapter::BuildArmingPatternData method
author : windows-driver-content
description : The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.
old-location : audio\ikeyworddetectoroemadapter_buildarmingpatterndata.htm
old-project : audio
ms.assetid : F74DC3C3-C182-4BBA-93C8-95A73C58CFEF
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : BuildArmingPatternData method [Audio Devices], IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter interface [Audio Devices], BuildArmingPatternData method, BuildArmingPatternData method [Audio Devices], IKeywordDetectorOemAdapter interface, BuildArmingPatternData, audio.ikeyworddetectoroemadapter_buildarmingpatterndata, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::BuildArmingPatternData, IKeywordDetectorOemAdapter::BuildArmingPatternData
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : keyworddetectoroemadapter.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : KeywordDetectorOemAdapter.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : keyworddetectoroemadapter.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : KEYWORDID
---


# BuildArmingPatternData method
The <b>BuildArmingPatternData</b> method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.

## Syntax

````
HRESULT BuildArmingPatternData(
  [in]  IStream                     *ModelData,
  [in]  KEYWORDSELECTOR             *KeywordSelectors,
  [in]  ULONG                       NumKeywordSelectors,
  [out] SOUNDDETECTOR_PATTERNHEADER **ppPatternData = 0
);
````

## Parameters

`UserModelData`



`KeywordSelectors`

An array of <a href="..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md">KEYWORDSELECTOR</a> structures identifying the desired set of matches for the keyword detector to arm.

`NumKeywordSelectors`

The number of items in the <i>KeywordSelectors</i> array. Only one key word selector is supported and this field must be set to one.

`ppPatternData`

The pattern data for the operating system to pass to the audio driver. The OEMDLL allocates the memory calling <a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>. The operating system will free the memory by calling <a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>.


## Return Value

This method can return one of these values.
<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>S_OK</dt>
</dl>
</td>
<td width="60%">
The function exited successfully. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>E_POINTER</dt>
</dl>
</td>
<td width="60%">
 The <i>ModelData</i> pointer is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>E_INVALIDARG</dt>
</dl>
</td>
<td width="60%">
 The <i>KeywordId</i> or <i>LangId</i> parameters are invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>HRESULT_FROM_WIN32(ERROR_GEN_FAILURE)</dt>
</dl>
</td>
<td width="60%">
 The processing was unable to complete.

</td>
</tr>
</table>

## Remarks

The operating system may call this method at any time. The operating system may also store the returned pattern data to reuse later for the same set of keyword selectors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | keyworddetectoroemadapter.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\keyworddetectoroemadapter\ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md">KEYWORDSELECTOR</a>

<a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>

<a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>

<a href="..\keyworddetectoroemadapter\nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md">IKeywordDetectorOemAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IKeywordDetectorOemAdapter::BuildArmingPatternData method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>