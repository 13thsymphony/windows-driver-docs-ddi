---
UID: NS.COMPSTUI._OPTTYPE
title: _OPTTYPE
author: windows-driver-content
description: The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure.
old-location: print\opttype.htm
old-project: print
ms.assetid: 041dd438-e837-4912-bda7-de654204198b
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: _OPTTYPE, OPTTYPE, *POPTTYPE
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
req.alt-api: OPTTYPE
req.alt-loc: compstui.h
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
---

# _OPTTYPE structure



## -description
The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a <a href="https://msdn.microsoft.com/572330d6-1a1b-46fd-bfb4-be2b0990bca4">property sheet option</a>, if the option is specified by an <a href="print.optitem">OPTITEM</a> structure.


## -syntax

````
typedef struct _OPTTYPE {
  WORD      cbSize;
  BYTE      Type;
  BYTE      Flags;
  WORD      Count;
  WORD      BegCtrlID;
  POPTPARAM pOptParam;
  WORD      Style;
  WORD      wReserved[3];
  ULONG_PTR dwReserved[3];
} OPTTYPE, *POPTTYPE;
````


## -struct-fields

### -field cbSize

Size, in bytes, of the OPTTYPE structure.

### -field Type

Specifies the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.

### -field Flags

Optional bit flags that modify the option's characteristics. The following flags can be set in any combination.


### -field OPTTF_NOSPACE_BEFORE_POSTFIX

CPSUI should not add a space character between the string specified by the <a href="print.optitem">OPTITEM</a> structure's <b>pName</b> string and the <a href="print.optparam">OPTPARAM</a> structure's <b>pData</b> string, when displaying the option.
Valid only if the option type is or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562847">TVOT_SCROLLBAR</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562848">TVOT_TRACKBAR</a>.
</dd>
</dl>


### -field OPTTF_TYPE_DISABLED

All the OPTPARAM structures to which <b>pOptParam</b> points are disabled, so that none of the parameter values are user-selectable.
</dd>
</dl>

### -field Count

Specifies the number of <a href="print.optparam">OPTPARAM</a> structures to which <b>pOptParam</b> points. This member's value is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.

### -field BegCtrlID

If <b>pDlgPage</b> in <a href="print.compropsheetui">COMPROPSHEETUI</a> identifies a CPSUI-supplied page, or if <b>DlgTemplateID</b> in <a href="print.dlgpage">DLGPAGE</a> identifies a CPSUI-supplied template, <b>BegCtrlID</b> is not used.
Otherwise, <b>BegCtrlID</b> must contain the first of a sequentially numbered set of Windows control identifiers. Control identifier usage is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.

### -field pOptParam

Pointer to an array of <a href="print.optparam">OPTPARAM</a> structures describing the parameter values that a user can select for the option.

### -field Style

Specifies flags that can be used to modify the option's display characteristics. The flags that can be specified are dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.

### -field wReserved

Reserved, must be initialized to zero.

### -field dwReserved

Reserved, must be initialized to zero.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Compstui.h (include Compstui.h)</dt>
</dl>
</td>
</tr>
</table>