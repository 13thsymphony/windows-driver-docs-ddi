---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface
title: IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.
old-location: print\iprintoemprintticketprovider_publishprinttickethelperinterface.htm
old-project: print
ms.assetid: d7512da3-eb47-4e22-9df8-b152b39cbcad
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface, PublishPrintTicketHelperInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface
req.alt-loc: prcomoem.h
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method



## -description
The <code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code> method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.



## -syntax

````
HRESULT PublishPrintTicketHelperInterface(
  [in] IUnknown *pHelper
);
````


## -parameters

### -param pHelper [in]

A pointer to an <b>IUnknown</b> interface, which should be cast to one of the following interfaces: For Unidrv plug-ins, the print ticket helper interface is <b>IPrintCoreHelperUni</b>; for Pscript5 plug-ins, the print ticket helper interface is <b>IPrintCoreHelperPS</b>.


## -returns
<code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.


## -remarks
If the plug-in maintains a handle to the helper object, the plug-in is responsible for later releasing that handle when it is no longer needed. 

If <code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code>  uses the helper interface, it should cache a pointer to the interface, and increment the reference count (by means of a call to the interface's <b>AddRef</b> method). If this method successfully increments the reference count, it should return S_OK. 


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
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>