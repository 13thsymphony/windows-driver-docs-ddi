---
UID: NF:filterpipeline.IPrintPipelineProgressReport.ReportProgress
title: IPrintPipelineProgressReport::ReportProgress method
author: windows-driver-content
description: The ReportProgress method reports the progress of the XPS job consumption to the pipeline manager.
old-location: print\iprintpipelineprogressreport_reportprogress.htm
old-project: print
ms.assetid: 989e8888-3494-4355-a41f-2ed774a060d2
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: ReportProgress method [Print Devices], filterpipeline/IPrintPipelineProgressReport::ReportProgress, ReportProgress, IPrintPipelineProgressReport interface [Print Devices], ReportProgress method, IPrintPipelineProgressReport::ReportProgress, print.iprintpipelineprogressreport_reportprogress, filterpipeline_3f4798ee-db6e-42ab-9eb8-fb016920fd08.xml, ReportProgress method [Print Devices], IPrintPipelineProgressReport interface, IPrintPipelineProgressReport
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IPrintPipelineProgressReport.ReportProgress
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# ReportProgress method
The <code>ReportProgress</code> method reports the progress of the XPS job consumption to the pipeline manager.

## Syntax

````
HRESULT ReportProgress(
  [in] EXpsJobConsumption update
);
````

## Parameters

`update`

An <a href="..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0003.md">EXpsJobConsumption</a>-typed value that describes the progress to the pipeline manager.


## Return Value

<code>ReportProgress</code> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |

## See Also

<a href="..\filterpipeline\nn-filterpipeline-iprintpipelineprogressreport.md">IPrintPipelineProgressReport</a>



<a href="..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0003.md">EXpsJobConsumption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintPipelineProgressReport::ReportProgress method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>