---
UID : NF:wiamdef.wiasSetItemPropNames
title : wiasSetItemPropNames function
author : windows-driver-content
description : The wiasSetItemPropNames function writes property names to item properties.
old-location : image\wiassetitempropnames.htm
old-project : image
ms.assetid : 4140a6c6-60e8-41ec-8de0-cfb56e757e34
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiamdef/wiasSetItemPropNames, wiasSetItemPropNames function [Imaging Devices], wiasSetItemPropNames, image.wiassetitempropnames, wiasFncs_e8f17c14-47a7-42bc-ad85-cdd52ecbab79.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiamdef.h
req.include-header : Wiamdef.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wiaservc.lib
req.dll : Wiaservc.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2"
req.product : Windows 10 or later.
---


# wiasSetItemPropNames function
The <b>wiasSetItemPropNames </b>function writes property names to item properties.

## Syntax

````
HRESULT _stdcall wiasSetItemPropNames(
  _In_    BYTE     *pWiasContext,
          LONG     cItemProps,
  _Inout_ PROPID   *ppId,
  _Inout_ LPOLESTR *ppSzNames
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`cItemProps`

Specifies the number of property names to write.

`ppId`

Pointer to the first element of a caller-allocated array of property identifiers (PROPIDs).

`ppszNames`

TBD


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

Minidrivers typically use this function when initializing item properties. The order of property identifiers in <i>ppId</i> must match the order of property names in <i>ppSzNames</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wiamdef\nf-wiamdef-wiassetitempropattribs.md">wiasSetItemPropAttribs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetItemPropNames function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>