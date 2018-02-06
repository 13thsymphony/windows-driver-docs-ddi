---
UID: NS:compstui._OIEXT
title: "_OIEXT"
author: windows-driver-content
description: The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an OPTITEM structure.
old-location: print\oiext.htm
old-project: print
ms.assetid: 932e5520-0ebf-4cfa-893a-a7eb969cb697
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: cpsuifnc_3abbb233-5393-4e23-a206-0474cfd6d7f1.xml, POIEXT structure pointer [Print Devices], OIEXT structure [Print Devices], compstui/POIEXT, _OIEXT, POIEXT, print.oiext, *POIEXT, OIEXT, compstui/OIEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	compstui.h
apiname:
-	OIEXT
product: Windows
targetos: Windows
req.typenames: "*POIEXT, OIEXT"
---

# _OIEXT structure
The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure.

## Syntax
````
typedef struct _OIEXT {
  WORD      cbSize;
  WORD      Flags;
  HINSTANCE hInstCaller;
  LPTSTR    pHelpFile;
  ULONG_PTR dwReserved[4];
} OIEXT, *POIEXT;
````

## Members


`cbSize`

Size, in bytes, of the OIEXT structure.

`dwReserved`

Reserved, must be initialized to zero.

`Flags`

Can contain the following bit flag:
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
OIEXTF_ANSI_STRING

</td>
<td>
If set, <b>pHelpFile</b> points to an ANSI string.

If not set, <b>pHelpFile</b> points to a Unicode string.

CPSUI does not check this flag if <b>pHelpFile</b> specifies a resource ID.

</td>
</tr>
</table>

`hInstCaller`

Instance handle to a DLL containing string and icon resources belonging to the <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a>, <a href="..\compstui\ns-compstui-_opttype.md">OPTTYPE</a>, and <a href="..\compstui\ns-compstui-_optparam.md">OPTPARAM</a> structures associated with the OIEXT structure. If <b>NULL</b>, CPSUI obtains resources from the DLL identified by the <b>hInstCaller</b> member of a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.

`pHelpFile`

Pointer to a NULL-terminated string representing a path to a help file containing help information for the option. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero. If <b>NULL</b>, CPSUI uses the help file identified by the <b>pHelpFile</b> member of a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | compstui.h (include Compstui.h) |