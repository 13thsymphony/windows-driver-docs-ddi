---
UID : NF:filterpipeline.IPrintPipelineFilter.ShutdownOperation
title : IPrintPipelineFilter::ShutdownOperation method
author : windows-driver-content
description : The Pipeline Manager uses the ShutdownOperation method to shut down a filter if the print job is canceled or an error occurs.
old-location : print\iprintpipelinefilter_shutdownoperation.htm
old-project : print
ms.assetid : 4df9721f-19d1-4070-92dd-45d41b7c5374
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ShutdownOperation, IPrintPipelineFilter interface [Print Devices], ShutdownOperation method, IPrintPipelineFilter, ShutdownOperation method [Print Devices], IPrintPipelineFilter interface, print.iprintpipelinefilter_shutdownoperation, filterpipeline/IPrintPipelineFilter::ShutdownOperation, IPrintPipelineFilter::ShutdownOperation, filterpipeline_5635f15b-3779-42ef-8b8d-3afeab1bab17.xml, ShutdownOperation method [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : filterpipeline.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : Filterpipeline.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : filterpipeline.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md">IPrintPipelineFilter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554306">IPrintPipelineManagerControl::FilterFinished</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintPipelineFilter::ShutdownOperation method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>