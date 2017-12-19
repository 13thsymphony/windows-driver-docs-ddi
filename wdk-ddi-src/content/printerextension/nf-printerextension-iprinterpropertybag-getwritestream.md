---
UID: NF.printerextension.IPrinterPropertyBag.GetWriteStream
title: IPrinterPropertyBag::GetWriteStream method
author: windows-driver-content
description: Gets a stream in order to write a stream property.
old-location: print\iprinterpropertybag_getwritestream.htm
old-project: print
ms.assetid: 47F535C0-57C7-407B-B47B-188EB6434F2E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag::GetWriteStream, GetWriteStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterPropertyBag.GetWriteStream
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

# IPrinterPropertyBag::GetWriteStream method



## -description
Gets a stream in order to write a stream property.



## -syntax

````
HRESULT GetWriteStream(
  [in]          BSTR     bstrName,
  [out, retval] IStream **ppValueStream
);
````


## -parameters

### -param  bstrName [in]

The property to write.


### -param ppValueStream [out, retval]

The retrieved stream.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks
This method does not work with non-stream properties.


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
<dt>Printerextension.h (include Printerextension.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::GetWriteStream method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

