---
UID: NF.prcomoem.IPrintOemPrintTicketProvider.BindPrinter
title: IPrintOemPrintTicketProvider::BindPrinter method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::BindPrinter method enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device.
old-location: print\iprintoemprintticketprovider_bindprinter.htm
old-project: print
ms.assetid: 6b31b340-de94-4e6c-a48a-7c1b874eb7cd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider::BindPrinter, BindPrinter
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
req.alt-api: IPrintOemPrintTicketProvider.BindPrinter
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
req.product: Windows 10 or later.
---

# IPrintOemPrintTicketProvider::BindPrinter method



## -description
The <code>IPrintOemPrintTicketProvider::BindPrinter</code> method enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device. This method also allows the plug-in to cache information (such as the printer handle) that can be used at a later time.



## -syntax

````
HRESULT BindPrinter(
  [in]  HANDLE     hPrinter,
  [in]  INT        version,
  [out] POEMPTOPTS pOptions,
  [out] INT        *cNamespaces,
  [out] BSTR       **ppNamespaces
);
````


## -parameters

### -param hPrinter [in]

The spooler's print handle, which is supplied by Unidrv. The provider should not close this handle at any time, because the client of the provider is responsible for managing the lifetime of this handle. The provider can cache the print handle; all future calls on this object are relative to the printer that is associated with this handle.


### -param version [in]

The major version number of the print schema. Windows Vista supports only version 1.


### -param pOptions [out]

A pointer to a variable that receives one of the following enumerated values: 




### -param OEMPT_DEFAULT

The system places a binary encoding (a binary large object [BLOB]) of the private <a href="display.devmodew">DEVMODEW</a> structure into the print ticket in a conversion of a DEVMODEW to a print ticket. 


### -param OEMPT_NOSNAPSHOT

The system will not place a binary encoding (a BLOB) of the private DEVMODEW structure into the print ticket in a conversion of a DEVMODEW to a print ticket. Use this value if all of the public and private DEVMODEW members are fully represented in the print ticket.

</dd>
</dl>
The OEM object that is being called should set the value pointed to by this parameter.


### -param cNamespaces [out]

A pointer to a variable that receives the number of private namespace URIs that are used in the plug-in. This number represents the count of strings in the array that is pointed to by *<i>ppNamespaces</i>.


### -param ppNamespaces [out]

A pointer to a variable that receives the address of the first element of a BSTR array. The plug-in fills each array position with a namespace URI. For more information about this parameter, see the following Remarks section.


## -returns
<code>IPrintOemPrintTicketProvider::BindPrinter</code> should return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_VERSION_NOT_SUPPORTED</b></dt>
</dl>The plug-in does not support the version of the print schema that is specified in the <i>version</i> parameter.

 


## -remarks
The plug-in is responsible for allocating memory for the array that is pointed to by the <i>ppNamespaces</i> parameter and for the namespace URI strings. The array should be allocated by using the <b>CoTaskMemAlloc</b> function; the namespace strings should be allocated by using the <b>SysAllocString</b> function. Both of these functions are described in the Microsoft Windows SDK documentation. The array that is pointed to by the <i>ppNamespaces</i> parameter is not required to contain the namespaces for the Print Schema Keywords or the Print Schema Framework.

Binding to a device enables the provider to cache certain objects and handles that it will need for future print ticket or print capabilities services on that device. For example, the printer handle in <i>hPrinter</i> can be cached. <code>IPrintOemPrintTicketProvider::BindPrinter</code> is guaranteed to be called only once. 

An <b>IPrintTicketProvider</b> object does not have to be able to bind more than once. The print ticket manager always uses different <b>IPrintTicketProvider</b> object instances for binding to different devices. All resources that are acquired in a successful call to <code>IPrintTicketProvider::BindPrinter</code> should be released when the reference count of an <b>IPrintTicketProvider</b> object is zero. (Note that the provider should not close the handle that was passed into the call to <b>BindPrinter</b>). The print ticket manager might create multiple providers for the same device, in different versions, if multiple versions are supported.


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

## -see-also
<dl>
<dt>
<a href="print.iprintoemprintticketprovider_convertdevmodetoprintticket">IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</a>
</dt>
<dt>
<a href="print.iprintoemprintticketprovider_convertprinttickettodevmode">IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</a>
</dt>
<dt>
<a href="print.iprintoemprintticketprovider_getsupportedversions">IPrintOemPrintTicketProvider::GetSupportedVersions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPrintTicketProvider::BindPrinter method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

