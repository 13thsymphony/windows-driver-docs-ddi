---
UID: NF:prcomoem.IPrintCoreHelperPS.CreateInstanceOfMSXMLObject
title: IPrintCoreHelperPS::CreateInstanceOfMSXMLObject method
author: windows-driver-content
description: The IPrintCoreHelperPS::CreateInstanceOfMSXMLObject method creates an instance of an MSXML object.
old-location: print\iprintcorehelperps_createinstanceofmsxmlobject.htm
old-project: print
ms.assetid: 017f6e00-694b-4ada-86be-cf2be047fa88
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintCoreHelperPS, IPrintCoreHelperPS::CreateInstanceOfMSXMLObject, CreateInstanceOfMSXMLObject
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
req.alt-api: IPrintCoreHelperPS.CreateInstanceOfMSXMLObject
req.alt-loc: Prcomoem.h
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

# IPrintCoreHelperPS::CreateInstanceOfMSXMLObject method



## -description
The <b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> method creates an instance of an MSXML object. 



## -syntax

````
STDMETHOD CreateInstanceOfMSXMLObject(
  [in]  REFCLSID  rclsid,
  [in]  LPUNKNOWN pUnkOuter,
  [in]  DWORD     dwClsContext,
  [in]  REFIID    riid,
  [out] LPVOID    ppv
);
````


## -parameters

### -param rclsid [in]

The CLSID that is associated with the data and code that will be used to create the object. 


### -param pUnkOuter [in]

A pointer to the aggregate object's <b>IUnknown</b> interface (the controlling <b>IUnknown</b>). This parameter must be <b>NULL</b>, which means that the object is not being created as part of an aggregate. 


### -param dwClsContext [in]

The context in which the code that manages the newly created object will run. The only valid values are <b>NULL</b> and CLSCTX_INPROC_SERVER, which is a value of the CLSCTX enumeration (described in the Microsoft Windows SDK documentation).


### -param riid [in]

A reference to the identifier of the interface that will be used to communicate with the object. 


### -param ppv [out]

A pointer to a memory address that receives the address of the interface that is requested in the <i>riid</i> parameter. If <b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> successfully returns, *<i>ppv</i> contains the address of the requested interface. If this method fails, *<i>ppv</i> contains <b>NULL</b>. 


## -returns
<b>IPrintCoreHelperPS::CreateInstanceOfMSXMLObject</b> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>An instance of the specified object class was successfully created.
<dl>
<dt><b>CLASS_E_NOAGGREGATION</b></dt>
</dl>The specified class cannot be created as part of an aggregate.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The specified class does not implement the requested interface, or the controlling <b>IUnknown</b> interface does not expose the requested interface.
<dl>
<dt><b>REGDB_E_CLASSNOTREG</b></dt>
</dl>A specified class is not registered in the registration database. This value can also indicate that the type of server you requested in the CLSCTX enumeration type is not registered or the values for the server types in the registry are corrupt.

 


## -remarks
The plug-in should not directly create an MSXML object by calling CoCreateInstance (described in the Windows SDK documentation). Instead, it should call Pscript to do so. The reason is that under certain conditions in which the printer driver might be used, such as with older operating system versions, the operating system does not need to register the required version of MSXML, which currently is version 6. In such situations, calling CoCreateInstance can fail. However, the core driver ensures that wherever the driver is present, the MSXML parser DLL is also present on the machine, making it possible to create an MSXML object when needed.


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