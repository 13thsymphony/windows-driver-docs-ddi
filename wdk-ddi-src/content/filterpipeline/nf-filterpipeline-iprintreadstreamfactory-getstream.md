---
UID: NF:filterpipeline.IPrintReadStreamFactory.GetStream
title: IPrintReadStreamFactory::GetStream method
author: windows-driver-content
description: The GetStream method gets the stream interface.
old-location: print\iprintreadstreamfactory_getstream.htm
old-project: print
ms.assetid: 47447f00-a57d-4821-b10e-1b2cf7eaad94
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IPrintReadStreamFactory::GetStream, filterpipeline_0e4b4a26-da03-4719-bbce-2bb160a882e2.xml, print.iprintreadstreamfactory_getstream, GetStream, IPrintReadStreamFactory interface [Print Devices], GetStream method, GetStream method [Print Devices], IPrintReadStreamFactory interface, IPrintReadStreamFactory, filterpipeline/IPrintReadStreamFactory::GetStream, GetStream method [Print Devices]
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
-	IPrintReadStreamFactory.GetStream
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# GetStream method
The <code>GetStream</code> method gets the stream interface.

## Syntax

````
HRESULT GetStream(
  [out] IPrintReadStream **ppStream
);
````

## Parameters

`ppStream`

A pointer to an <a href="..\filterpipeline\nn-filterpipeline-iprintreadstream.md">IPrintReadStream</a> interface. The filter can use this interface to read the contents of the print ticket.


## Return Value

<code>GetStream</code> returns an <b>HRESULT</b> value.

## Remarks

The following code example shows how a filter can use <b>IPrintReadStreamFactory</b> to access the per-user print ticket.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VARIANT var;
VariantInit(&amp;var);

HRESULT hr = pIPropertyBag-&gt;GetProperty(
  XPS_FP_USER_PRINT_TICKET,
  &amp;var);

if (SUCCEEDED(hr))
{
 IPrintReadStreamFactory   *pPrintReadStreamFactory;

 hr = V_UNKNOWN(&amp;var)-&gt;QueryInterface(
 IID_IPrintReadStreamFactory,
 reinterpret_cast&lt;void **&gt;(&amp;pPrintReadStreamFactory));

 if (SUCCEEDED(hr))
    {
 IPrintReadStream *pPrintTicketStream;

 hr = pPrintReadStreamFactory-&gt;GetStream(&amp;pPrintTicketStream);

 if (SUCCEEDED(hr))
      {

       // Use the print ticket here. 
       // It's OK to cache the pointer 
       // to use now and release later.

 pPrintTicketStream-&gt;Release();
      }

 pPrintReadStreamFactory-&gt;Release();
    }

 VariantClear(&amp;var);
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |