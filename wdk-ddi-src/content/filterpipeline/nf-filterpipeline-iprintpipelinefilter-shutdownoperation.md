---
UID: NF:filterpipeline.IPrintPipelineFilter.ShutdownOperation
title: IPrintPipelineFilter::ShutdownOperation method
author: windows-driver-content
description: The Pipeline Manager uses the ShutdownOperation method to shut down a filter if the print job is canceled or an error occurs.
old-location: print\iprintpipelinefilter_shutdownoperation.htm
old-project: print
ms.assetid: 4df9721f-19d1-4070-92dd-45d41b7c5374
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintPipelineFilter, IPrintPipelineFilter interface [Print Devices], ShutdownOperation method, IPrintPipelineFilter::ShutdownOperation, ShutdownOperation method [Print Devices], ShutdownOperation method [Print Devices], IPrintPipelineFilter interface, ShutdownOperation,IPrintPipelineFilter.ShutdownOperation, filterpipeline/IPrintPipelineFilter::ShutdownOperation, filterpipeline_5635f15b-3779-42ef-8b8d-3afeab1bab17.xml, print.iprintpipelinefilter_shutdownoperation
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Filterpipeline.h
api_name:
-	IPrintPipelineFilter.ShutdownOperation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# ShutdownOperation method
The Pipeline Manager uses the <code>ShutdownOperation</code> method to shut down a filter if the print job is canceled or an error occurs.

## Syntax

````
HRESULT STDMETHODCALLTYPE ShutdownOperation(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

<code>ShutdownOperation</code> returns an <b>HRESULT</b> value.

## Remarks

The <code>ShutdownOperation</code> method is called by the pipeline manager if the job is canceled or an error occurs. Filters do not have to block this call until they completely finish using any resources. You should set up an internal state to indicate when filters need to cancel a job. Filters must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554306">IPrintPipelineManagerControl::FilterFinished</a> when the filters are finished, which can be later.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md">IPrintPipelineFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554306">IPrintPipelineManagerControl::FilterFinished</a>