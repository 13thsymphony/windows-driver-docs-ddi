---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface
title: IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.
old-location: print\iprintoemprintticketprovider_publishprinttickethelperinterface.htm
old-project: print
ms.assetid: d7512da3-eb47-4e22-9df8-b152b39cbcad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], PublishPrintTicketHelperInterface method, IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface, PublishPrintTicketHelperInterface, PublishPrintTicketHelperInterface method [Print Devices], PublishPrintTicketHelperInterface method [Print Devices], IPrintOemPrintTicketProvider interface, PublishPrintTicketHelperInterface,IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface, prcomoem/IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface, print.iprintoemprintticketprovider_publishprinttickethelperinterface, print_ticket-package_b314b169-8111-4320-89fc-a99fb6e30639.xml
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
-	prcomoem.h
api_name:
-	IPrintOemPrintTicketProvider.PublishPrintTicketHelperInterface
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface method
The <code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code> method publishes the print ticket helper interface for either Unidrv or Pscript5 user interface (UI) plug-ins.

## Syntax

```
HRESULT PublishPrintTicketHelperInterface(
  IUnknown *pHelper
);
```

## Parameters

`pHelper`

A pointer to an <b>IUnknown</b> interface, which should be cast to one of the following interfaces: For Unidrv plug-ins, the print ticket helper interface is <b>IPrintCoreHelperUni</b>; for Pscript5 plug-ins, the print ticket helper interface is <b>IPrintCoreHelperPS</b>.


## Return Value

<code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## Remarks

If the plug-in maintains a handle to the helper object, the plug-in is responsible for later releasing that handle when it is no longer needed. 

If <code>IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface</code>  uses the helper interface, it should cache a pointer to the interface, and increment the reference count (by means of a call to the interface's <b>AddRef</b> method). If this method successfully increments the reference count, it should return S_OK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |