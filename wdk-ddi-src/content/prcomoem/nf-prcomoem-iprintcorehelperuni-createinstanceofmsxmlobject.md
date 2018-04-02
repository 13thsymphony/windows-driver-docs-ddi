---
UID: NF:prcomoem.IPrintCoreHelperUni.CreateInstanceOfMSXMLObject
title: IPrintCoreHelperUni::CreateInstanceOfMSXMLObject method
author: windows-driver-content
description: The IPrintCoreHelperUni::CreateInstanceOfMSXMLObject method creates an instance of an MSXML object.
old-location: print\iprintcorehelperuni_createinstanceofmsxmlobject.htm
old-project: print
ms.assetid: 801ad433-4d52-4947-93f5-a11521a4df18
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateInstanceOfMSXMLObject method [Print Devices], CreateInstanceOfMSXMLObject method [Print Devices], IPrintCoreHelperUni interface, CreateInstanceOfMSXMLObject,IPrintCoreHelperUni.CreateInstanceOfMSXMLObject, IPrintCoreHelperUni, IPrintCoreHelperUni interface [Print Devices], CreateInstanceOfMSXMLObject method, IPrintCoreHelperUni::CreateInstanceOfMSXMLObject, prcomoem/IPrintCoreHelperUni::CreateInstanceOfMSXMLObject, print.iprintcorehelperuni_createinstanceofmsxmlobject, print_unidrv-pscript_allplugins_b6f2207a-4289-4a1f-ae2d-accc80c68a79.xml
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
-	Prcomoem.h
api_name:
-	IPrintCoreHelperUni.CreateInstanceOfMSXMLObject
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# IPrintCoreHelperUni::CreateInstanceOfMSXMLObject method
The <code>IPrintCoreHelperUni::CreateInstanceOfMSXMLObject</code> method creates an instance of an MSXML object.

## Syntax

```
HRESULT CreateInstanceOfMSXMLObject(
  IN REFCLSID  rclsid,
  IN LPUNKNOWN pUnkOuter,
  IN DWORD     dwClsContext,
  IN REFIID    riid,
  OUT LPVOID   *ppv
);
```

## Parameters

`rclsid`

The CLSID that is associated with the data and code that will be used to create the object.

`pUnkOuter`

A pointer to the aggregate object's <b>IUnknown</b> interface (the controlling <b>IUnknown</b>). This parameter must be <b>NULL</b>, which means that the object is not being created as part of an aggregate.

`dwClsContext`

The context in which the code that manages the newly created object will run. The only valid values are <b>NULL</b> and CLSCTX_INPROC_SERVER, which is a value of the CLSCTX enumeration (described in the Microsoft Windows SDK documentation).

`riid`

A reference to the identifier of the interface that will be used to communicate with the object.

`ppv`

A pointer to a memory address that receives the address of the interface that is requested in the <i>riid</i> parameter. If <code>IPrintCoreHelperUni::CreateInstanceOfMSXMLObject</code> successfully returns, *<i>ppv</i> contains the address of the requested interface. If this method fails, *<i>ppv</i> contains <b>NULL</b>.


## Return Value

<code>IPrintCoreHelperUni::CreateInstanceOfMSXMLObject</code> should return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
An instance of the specified object class was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CLASS_E_NOAGGREGATION</b></dt>
</dl>
</td>
<td width="60%">
The specified class cannot be created as part of an aggregate.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The specified class does not implement the requested interface, or the controlling <b>IUnknown</b> interface does not expose the requested interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>REGDB_E_CLASSNOTREG</b></dt>
</dl>
</td>
<td width="60%">
A specified class is not registered in the registration database. This value can also indicate that the type of server you requested in the CLSCTX enumeration type is not registered or the values for the server types in the registry are corrupt.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |