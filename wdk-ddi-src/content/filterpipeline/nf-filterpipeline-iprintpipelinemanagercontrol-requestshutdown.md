---
UID: NF:filterpipeline.IPrintPipelineManagerControl.RequestShutdown
title: IPrintPipelineManagerControl::RequestShutdown method
author: windows-driver-content
description: The RequestShutdown method requests that a pipeline be shut down.
old-location: print\iprintpipelinemanagercontrol_requestshutdown.htm
old-project: print
ms.assetid: dfb0d7d1-4e82-4471-814b-4b8c4929c709
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintPipelineManagerControl, IPrintPipelineManagerControl::RequestShutdown, RequestShutdown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintPipelineManagerControl.RequestShutdown
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: EXpsFontRestriction
---

# IPrintPipelineManagerControl::RequestShutdown method



## -description
The <code>RequestShutdown</code> method requests that a pipeline be shut down.



## -syntax

````
HRESULT RequestShutdown(
  [in] HRESULT       hrReason,
  [in] IImgErrorInfo *pReason
);
````


## -parameters

### -param hrReason [in]

An <b>HRESULT</b> value that indicates the reason for the lack of memory.


### -param pReason [in]

Not used. Set to <b>NULL</b>.


## -returns
<code>RequestShutdown</code> returns an <b>HRESULT</b> value.


## -remarks
A filter that uses the <a href="..\filterpipeline\nn-filterpipeline-ixpsdocumentconsumer.md">IXpsDocumentConsumer</a> interface must call <code>IPrintPipelineManagerControl::RequestShutdown</code> before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556293">IXpsDocumentConsumer::CloseSender</a> to shut down the pipeline. Calling <b>IXpsDocumentConsumer::CloseSender</b> first can produce an invalid XPS document and cause an error. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IDL

</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>