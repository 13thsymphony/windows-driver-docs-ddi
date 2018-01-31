---
UID : NS:compstui._PROPSHEETUI_GETICON_INFO
title : "_PROPSHEETUI_GETICON_INFO"
author : windows-driver-content
description : The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON.
old-location : print\propsheetui_geticon_info.htm
old-project : print
ms.assetid : 23c06f1c-0c8f-4055-a997-1ff94c4a541e
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PPROPSHEETUI_GETICON_INFO structure pointer [Print Devices], _PROPSHEETUI_GETICON_INFO, PROPSHEETUI_GETICON_INFO, compstui/PROPSHEETUI_GETICON_INFO, compstui/PPROPSHEETUI_GETICON_INFO, cpsuifnc_da228e66-0d1b-4d35-af1e-e1b99e56ad08.xml, PPROPSHEETUI_GETICON_INFO, print.propsheetui_geticon_info, *PPROPSHEETUI_GETICON_INFO, PROPSHEETUI_GETICON_INFO structure [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : compstui.h
req.include-header : Compstui.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PROPSHEETUI_GETICON_INFO, *PPROPSHEETUI_GETICON_INFO
---

# _PROPSHEETUI_GETICON_INFO structure
The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a>-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON.

## Syntax
````
typedef struct _PROPSHEETUI_GETICON_INFO {
  WORD  cbSize;
  WORD  Flags;
  WORD  cxIcon;
  WORD  cyIcon;
  HICON hIcon;
} PROPSHEETUI_GETICON_INFO, *PPROPSHEETUI_GETICON_INFO;
````

## Members


`cbSize`

CPSUI-supplied size, in bytes, of the PROPSHEETUI_GETICON_INFO structure.

`cxIcon`

CPSUI-supplied icon width, in pixels.

`cyIcon`

CPSUI-supplied icon height, in pixels.

`Flags`

Reserved.

`hIcon`

Receives an application-supplied icon handle. If the icon is not loaded, the member must be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | compstui.h (include Compstui.h) |