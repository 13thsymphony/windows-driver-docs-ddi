---
UID: NN:filterpipeline.IPartFont
title: IPartFont
author: windows-driver-content
description: The IPartFont interface is the abstraction for fonts in a part.
old-location: print\ipartfont.htm
old-project: print
ms.assetid: bdb1ad56-de4c-4a9b-96b6-f9faff4abf65
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPartFont
req.alt-loc: filterpipeline.h
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
req.typenames: EXpsFontRestriction
---

# IPartFont interface



## -description
The <b>IPartFont</b> interface is the abstraction for fonts in a part.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPartFont</b> interface inherits from <a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>. <b>IPartFont</b> also has these types of members:

The <b>IPartFont</b> interface has these methods.

The <b>GetFontProperties</b> method gets the font properties.

The <b>SetFontContent</b> method sets the content of the font.

The <b>SetFontOptions</b> method sets the options for the font.

 


## -members
The <b>IPartFont</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551897">IPartFont::GetFontProperties</a>
</td>
<td align="left" width="63%">
The <b>GetFontProperties</b> method gets the font properties.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551901">IPartFont::SetFontContent</a>
</td>
<td align="left" width="63%">
The <b>SetFontContent</b> method sets the content of the font.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551904">IPartFont::SetFontOptions</a>
</td>
<td align="left" width="63%">
The <b>SetFontOptions</b> method sets the options for the font.

</td>
</tr>
</table>The <b>GetFontProperties</b> method gets the font properties.

The <b>SetFontContent</b> method sets the content of the font.

The <b>SetFontOptions</b> method sets the options for the font.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h (include Filterpipeline.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\filterpipeline\nn-filterpipeline-ipartbase.md">IPartBase</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPartFont interface%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

