---
UID: NF.filterpipeline.IFixedPage.SetPrintTicket
title: IFixedPage::SetPrintTicket method
author: windows-driver-content
description: The SetPrintTicket method associates a print ticket with the page.
old-location: print\ifixedpage_setprintticket.htm
old-project: print
ms.assetid: d899211a-e98d-45f6-9574-8b5f51658edf
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IFixedPage, IFixedPage::SetPrintTicket, SetPrintTicket
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
req.alt-api: IFixedPage.SetPrintTicket
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
---

# IFixedPage::SetPrintTicket method



## -description
The <b>SetPrintTicket</b> method associates a print ticket with the page.



## -syntax

````
HRESULT SetPrintTicket(
  [in] IPartPrintTicket *pPrintTicket
);
````


## -parameters

### -param pPrintTicket [in]

The print ticket object.


## -returns
<b>SetPrintTicket</b> returns an <b>HRESULT</b> value.


## -remarks


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