---
UID: NF:dbgeng.IDebugSymbols4.GetLineByInlineContextWide
title: IDebugSymbols4::GetLineByInlineContextWide
author: windows-driver-content
description: Gets a line by inline context.
old-location: debugger\idebugsymbols4_getlinebyinlinecontextwide.htm
old-project: debugger
ms.assetid: 5DCD8407-1C30-475F-9741-62DB9C86297B
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetLineByInlineContextWide, GetLineByInlineContextWide method [Windows Debugging], GetLineByInlineContextWide method [Windows Debugging],IDebugSymbols4 interface, IDebugSymbols4 interface [Windows Debugging],GetLineByInlineContextWide method, IDebugSymbols4.GetLineByInlineContextWide, IDebugSymbols4::GetLineByInlineContextWide, dbgeng/IDebugSymbols4::GetLineByInlineContextWide, debugger.idebugsymbols4_getlinebyinlinecontextwide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugSymbols4.GetLineByInlineContextWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols4::GetLineByInlineContextWide


## -description


Gets a line by inline context.


## -parameters




### -param Offset [in]

An offset for the line.


### -param InlineContext [in]

The inline context. 


### -param Line [out, optional]

A pointer to the returned line.


### -param FileBuffer [out]

A pointer to a buffer for a Unicode character string.


### -param FileBufferSize [in]

The size of the file buffer.


### -param FileSize [out, optional]

A pointer to the length of the file.


### -param Displacement [out, optional]

A pointer to the displacement value of the file.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/BE2734B5-1E67-4E38-B4DF-0C353BFB1F0B">IDebugSymbols4</a>
 

 

