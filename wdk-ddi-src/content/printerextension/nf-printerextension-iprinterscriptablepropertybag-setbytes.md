---
UID: NF.printerextension.IPrinterScriptablePropertyBag.SetBytes
title: IPrinterScriptablePropertyBag::SetBytes method
author: windows-driver-content
description: Writes a byte array property.
old-location: print\iprinterscriptablepropertybag_setbytes.htm
old-project: print
ms.assetid: 517CF135-A5D7-4C99-8592-59934E24DEE3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag::SetBytes, SetBytes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterScriptablePropertyBag.SetBytes
req.alt-loc: Printerextension.h
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

# IPrinterScriptablePropertyBag::SetBytes method



## -description
Writes a byte array property.



## -syntax

````
HRESULT SetBytes(
  [in] BSTR      bstrName,
  [in] IDispatch *pdispArray
);
````


## -parameters

### -param bstrName [in]

The array to write to.


### -param pdispArray [in]

The JavaScript array to write.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks
A call to <b>SetBytes</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::SetBytes method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

