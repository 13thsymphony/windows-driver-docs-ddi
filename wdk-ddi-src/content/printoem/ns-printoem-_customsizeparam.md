---
UID: NS.PRINTOEM._CUSTOMSIZEPARAM
title: _CUSTOMSIZEPARAM
author: windows-driver-content
description: The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer.
old-location: print\customsizeparam.htm
old-project: print
ms.assetid: 7ec0c38a-8614-417b-9ec3-678c7d80841f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _CUSTOMSIZEPARAM, CUSTOMSIZEPARAM, *PCUSTOMSIZEPARAM, PCUSTOMSIZEPARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CUSTOMSIZEPARAM
req.alt-loc: printoem.h
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

# _CUSTOMSIZEPARAM structure



## -description
The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer.



## -syntax

````
typedef struct _CUSTOMSIZEPARAM {
  LONG dwOrder;
  LONG lMinVal;
  LONG lMaxVal;
} CUSTOMSIZEPARAM, *PCUSTOMSIZEPARAM;
````


## -struct-fields

### -field dwOrder

Specifies the order in which a custom page size parameter is placed on the PostScript interpreter's operand stack. For example, a parameter for which <b>dwOrder</b> is set to 1 is placed on the stack first. A parameter for which <b>dwOrder</b> is set to 2 is placed on the stack second, and so on.


### -field lMinVal

Specifies the minimum value of the custom page size parameter.


### -field lMaxVal

Specifies the maximum value of the custom page size parameter.


## -remarks
The custom page size parameters include Width, Height, WidthOffset, HeightOffset, and Orientation. For Orientation, <b>lMinVal</b> and <b>lMaxVal</b> are values in the range [0, 3]. For the other custom page size parameters, <b>lMinVal</b> and <b>lMaxVal</b> values are in units of microns.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.eattribute_datatype">EATTRIBUTE_DATATYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20CUSTOMSIZEPARAM structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

