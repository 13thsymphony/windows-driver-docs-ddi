---
UID: NN:filterpipeline.IInterFilterCommunicator
title: IInterFilterCommunicator
author: windows-driver-content
description: The IInterFilterCommunicator interface is implemented in an object that resides in the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface.
old-location: print\iinterfiltercommunicator.htm
old-project: print
ms.assetid: 777da1db-5522-48fc-bf35-8e6bf9203d6a
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
req.alt-api: IInterFilterCommunicator
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

# IInterFilterCommunicator interface



## -description
The <b>IInterFilterCommunicator</b> interface is implemented in an object that resides in the PrintFilterPipelineSvc service and is made available to filters through methods in the <a href="..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md">IPrintPipelineFilter</a> interface.<b>IInterFilterCommunicator</b> inherits from the <b>IUnknown</b> interface.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IInterFilterCommunicator</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IInterFilterCommunicator</b> also has these types of members:

The <b>IInterFilterCommunicator</b> interface has these methods.

The <b>RequestReader</b> method retrieves the reader interface for an <b>IInterFilterCommunicator</b> object. 

The <b>RequestWriter</b> method retrieves the writer interface for an <b>IInterFilterCommunicator</b> object.

 


## -members
The <b>IInterFilterCommunicator</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551054">IInterFilterCommunicator::RequestReader</a>
</td>
<td align="left" width="63%">
The <b>RequestReader</b> method retrieves the reader interface for an <b>IInterFilterCommunicator</b> object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551057">IInterFilterCommunicator::RequestWriter</a>
</td>
<td align="left" width="63%">
The <b>RequestWriter</b> method retrieves the writer interface for an <b>IInterFilterCommunicator</b> object.

</td>
</tr>
</table>The <b>RequestReader</b> method retrieves the reader interface for an <b>IInterFilterCommunicator</b> object. 

The <b>RequestWriter</b> method retrieves the writer interface for an <b>IInterFilterCommunicator</b> object.

 


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