---
UID : NF:ks.KsFastPropertyHandler
title : KsFastPropertyHandler function
author : windows-driver-content
description : The KsFastPropertyHandler function handles fast property requests through IOCTL_KS_PROPERTY. It responds to all property identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.
old-location : stream\ksfastpropertyhandler.htm
old-project : stream
ms.assetid : 39a216f8-297d-45cc-9bec-4c0ee9941441
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsFastPropertyHandler
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsFastPropertyHandler
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
req.typenames : 
---


# KsFastPropertyHandler function
The <b>KsFastPropertyHandler</b> function handles fast property requests through IOCTL_KS_PROPERTY. It responds to all property identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.

## Syntax

````
KSDDKAPI BOOLEAN NTAPI KsFastPropertyHandler(void);
````

## Parameters

`FileObject`



`Property`



`PropertyLength`



`Data`



`DataLength`



`IoStatus`



`PropertySetsCount`



`PropertySet`




## Return Value

The <b>KsFastPropertyHandler</b> function returns <b>TRUE</b> if the request was handled, or <b>FALSE</b> if the request was not handled. If <b>FALSE</b> is returned, an IRP is generated. If the request was handled, the function sets the IoStatus-&gt;Information element, either through setting it to zero because of an internal error, or through a property handler setting it. The property handler also sets the IoStatus-&gt;Status field when the property is actually handled.

The <b>KsFastPropertyHandler</b> function returns <b>TRUE</b> if the request was handled, or <b>FALSE</b> if the request was not handled. If <b>FALSE</b> is returned, an IRP is generated. If the request was handled, the function sets the IoStatus-&gt;Information element, either through setting it to zero because of an internal error, or through a property handler setting it. The property handler also sets the IoStatus-&gt;Status field when the property is actually handled.

The <b>KsFastPropertyHandler</b> function returns <b>TRUE</b> if the request was handled, or <b>FALSE</b> if the request was not handled. If <b>FALSE</b> is returned, an IRP is generated. If the request was handled, the function sets the IoStatus-&gt;Information element, either through setting it to zero because of an internal error, or through a property handler setting it. The property handler also sets the IoStatus-&gt;Status field when the property is actually handled.

## Remarks

The owner of a property set can perform prefiltering or postfiltering of the property handling, as well as processing requests made through the fast I/O dispatch interface for device control. The <b>KsFastPropertyHandler</b> function is only used to process requests that can be fulfilled quickly.  The <i>Wait</i> parameter of the fast I/O function is not passed and is assumed to be <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFastPropertyHandler function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>