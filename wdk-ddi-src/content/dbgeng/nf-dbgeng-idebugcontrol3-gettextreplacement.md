---
UID: NF:dbgeng.IDebugControl3.GetTextReplacement
title: IDebugControl3::GetTextReplacement method
author: windows-driver-content
description: The GetTextReplacement method returns the value of a user-named alias or an automatic alias.
old-location: debugger\gettextreplacement.htm
old-project: debugger
ms.assetid: 8d5531ac-afa1-4928-8ea6-8be4663cf06a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::GetTextReplacement, GetTextReplacement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl2.GetTextReplacement,IDebugControl3.GetTextReplacement
req.alt-loc: dbgeng.h
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl3::GetTextReplacement method



## -description
The <b>GetTextReplacement</b>  method returns the value of a user-named alias or an automatic alias.  



## -syntax

````
HRESULT GetTextReplacement(
  [in, optional]  PCSTR  SrcText,
  [in]            ULONG  Index,
  [out, optional] PSTR   SrcBuffer,
  [in]            ULONG  SrcBufferSize,
  [out, optional] PULONG SrcSize,
  [out, optional] PSTR   DstBuffer,
  [in]            ULONG  DstBufferSize,
  [out, optional] PULONG DstSize
);
````


## -parameters

### -param SrcText [in, optional]

Specifies the name of the alias.  The engine first searches the user-named aliases for one with this name. Then, if no match is found, the automatic aliases are searched.  If <i>SrcText</i> is <b>NULL</b>, <i>Index</i> is used to specify the alias.


### -param Index [in]

Specifies the index of an alias.  The indexes of the user-named aliases come before the indexes of the automatic aliases.  <i>Index</i> is only used if <i>SrcText</i> is <b>NULL</b>.  <i>Index</i> can be used along with <a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a> to iterate over all the user-named and automatic aliases.


### -param SrcBuffer [out, optional]

Receives the name of the alias.  This is the name specified in <i>SrcText</i>, if <i>SrcText</i> is not <b>NULL</b>.  If <i>SrcBuffer</i> is <b>NULL</b>, this information is not returned.


### -param SrcBufferSize [in]

Specifies the size, in characters, of the <i>SrcBuffer</i> buffer.


### -param SrcSize [out, optional]

Receives the size, in characters, of the name of the alias.  If <i>SrcSize</i> is <b>NULL</b>, this information is not returned.


### -param DstBuffer [out, optional]

Receives the value of the alias specified by <i>SrcText</i> and <i>Index</i>.  If <i>DstBuffer</i> is <b>NULL</b>, this information is not returned.


### -param DstBufferSize [in]

Specifies the size, in characters, of the <i>DstBuffer</i> buffer.


### -param DstSize [out, optional]

Receives the size, in characters, of the value of the alias.  If <i>DstSize</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>SrcBuffer</i> with the value of the alias (specified by <i>DstBuffer</i>).

For an overview of aliases used by the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556818">SetTextReplacement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547988">GetNumberTextReplacements</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549270">GetTextMacro</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538014">al (List Aliases)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl2::GetTextReplacement method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

