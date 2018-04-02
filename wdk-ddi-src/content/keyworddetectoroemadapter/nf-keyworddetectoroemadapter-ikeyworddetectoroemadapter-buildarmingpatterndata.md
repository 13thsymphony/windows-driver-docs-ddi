---
UID: NF:keyworddetectoroemadapter.IKeywordDetectorOemAdapter.BuildArmingPatternData
title: IKeywordDetectorOemAdapter::BuildArmingPatternData method
author: windows-driver-content
description: The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.
old-location: audio\ikeyworddetectoroemadapter_buildarmingpatterndata.htm
old-project: audio
ms.assetid: F74DC3C3-C182-4BBA-93C8-95A73C58CFEF
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: BuildArmingPatternData method [Audio Devices], BuildArmingPatternData method [Audio Devices], IKeywordDetectorOemAdapter interface, BuildArmingPatternData,IKeywordDetectorOemAdapter.BuildArmingPatternData, IKeywordDetectorOemAdapter, IKeywordDetectorOemAdapter interface [Audio Devices], BuildArmingPatternData method, IKeywordDetectorOemAdapter::BuildArmingPatternData, audio.ikeyworddetectoroemadapter_buildarmingpatterndata, keyworddetectoroemadapter/IKeywordDetectorOemAdapter::BuildArmingPatternData
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	KeywordDetectorOemAdapter.h
api_name:
-	IKeywordDetectorOemAdapter.BuildArmingPatternData
product: Windows
targetos: Windows
req.typenames: KEYWORDID
---


# IKeywordDetectorOemAdapter::BuildArmingPatternData method
The <b>BuildArmingPatternData</b> method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection.

## Syntax

```
HRESULT BuildArmingPatternData(
  IStream                     *UserModelData,
  KEYWORDSELECTOR             *KeywordSelectors,
  ULONG                       NumKeywordSelectors,
  SOUNDDETECTOR_PATTERNHEADER **ppPatternData
);
```

## Parameters

`UserModelData`

A pointer to <b>IStream</b> bound to model data for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957511">KEYWORDSELECTOR</a> values in the <i>KeywordSelectors</i> parameter.

`KeywordSelectors`

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/dn957511">KEYWORDSELECTOR</a> structures identifying the desired set of matches for the keyword detector to arm.

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
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | keyworddetectoroemadapter.h |

## See Also

<a href="https://msdn.microsoft.com/c4cb588d-9482-4f90-a92e-75b604540d5c">CoTaskMemAlloc</a>



<a href="https://msdn.microsoft.com/3d0af12e-fc74-4ef7-b2dd-e9da5d0483c7">CoTaskMemFree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957504">IKeywordDetectorOemAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957511">KEYWORDSELECTOR</a>