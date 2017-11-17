---
UID: NF.filterpipeline.DrvPopulateFilterServices
title: DrvPopulateFilterServices
author: windows-driver-content
description: The DrvPopulateFilterServices function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate filter service objects in the filter pipeline property bag specified by the pPropertyBag parameter.
old-location: print\drvpopulatefilterservices.htm
ms.assetid: A24DAC54-57FE-419D-8B5D-54B8AFC338DE
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: print
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrvPopulateFilterServices
req.alt-loc: Filterpipeline.h
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
ms.keywords: DrvPopulateFilterServices
req.iface: 
---

# DrvPopulateFilterServices function



## -description
<p>The <b>DrvPopulateFilterServices</b> function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate  filter service objects in the filter pipeline property bag specified by the <i>pPropertyBag</i> parameter.</p>


## -syntax

````
HRESULT WINAPI DrvPopulateFilterServices(
  _In_ IPrintPipelinePropertyBag *pPropertyBag
);
````


## -parameters
<dl>

### -param <i>pPropertyBag</i> [in]

<dd>
<p>Pointer to a print pipeline property bag.</p>
</dd>
</dl>

## -returns
<p>This function returns an HRESULT value.</p>

## -remarks
<p>The <a href="https://msdn.microsoft.com/7567c514-3034-4db0-9622-31d14eb3772e">XPSDrv printer driver</a> can specify filter service provider module using the &lt;<i>FilterServiceProvider</i>&gt;  or &lt;<i>OptionalFilterServiceProvider</i>&gt; element in the <a href="NULL">filter pipeline configuration file</a>.   The service provider module must export the <b>DrvPopulateFilterServices</b> function.</p>

<p>The <a href="https://msdn.microsoft.com/7567c514-3034-4db0-9622-31d14eb3772e">XPSDrv printer driver</a> can specify filter service provider module using the &lt;<i>FilterServiceProvider</i>&gt;  or &lt;<i>OptionalFilterServiceProvider</i>&gt; element in the <a href="NULL">filter pipeline configuration file</a>.   The service provider module must export the <b>DrvPopulateFilterServices</b> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="NULL">Filter pipeline configuration file</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554320">IPrintPipelinePropertyBag</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7567c514-3034-4db0-9622-31d14eb3772e">XPSDrv printer driver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DrvPopulateFilterServices function%20 RELEASE:%20(10/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
