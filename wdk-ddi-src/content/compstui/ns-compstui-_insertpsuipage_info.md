---
UID: NS.COMPSTUI._INSERTPSUIPAGE_INFO
title: _INSERTPSUIPAGE_INFO
author: windows-driver-content
description: The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_INSERT_PSUIPAGE. All member values must be supplied by the ComPropSheet caller.
old-location: print\insertpsuipage_info.htm
old-project: print
ms.assetid: 99ec8cfa-3ec7-4080-b22a-dba0a86b7e4a
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _INSERTPSUIPAGE_INFO, *PINSERTPSUIPAGE_INFO, INSERTPSUIPAGE_INFO
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
req.alt-api: INSERTPSUIPAGE_INFO
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

# _INSERTPSUIPAGE_INFO structure



## -description
The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's <a href="print.compropsheet">ComPropSheet</a> function, if the function code is <a href="print.cpsfunc_insert_psuipage">CPSFUNC_INSERT_PSUIPAGE</a>. All member values must be supplied by the <b>ComPropSheet</b> caller.



## -syntax

````
typedef struct _INSERTPSUIPAGE_INFO {
  WORD      cbSize;
  BYTE      Type;
  BYTE      Mode;
  ULONG_PTR dwData1;
  ULONG_PTR dwData2;
  ULONG_PTR dwData3;
} INSERTPSUIPAGE_INFO, *PINSERTPSUIPAGE_INFO;
````


## -struct-fields

### -field cbSize

Caller-supplied size, in bytes, of the INSERTPSUIPAGE_INFO structure.


### -field Type

Caller-supplied integer value indicating the type of insertion being requested. The member can contain one of the following constants:




### -field PSUIPAGEINSERT_DLL

CPSUI calls the specified <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> typed function, with a reason value of PROPSHEETUI_REASON_INIT. The function is contained in a separate DLL.

</dd>
</dl>



### -field PSUIPAGEINSERT_GROUP_PARENT

CPSUI creates a new <a href="https://msdn.microsoft.com/b4c40c15-df16-4af0-81c8-9e70d26ba598">group parent</a>.

</dd>
</dl>



### -field PSUIPAGEINSERT_HPROPSHEETPAGE

CPSUI inserts a page that has been created by calling <b>CreatePropertySheetPage</b> (see the Microsoft Windows SDK documentation).

(This is equivalent to calling <a href="print.compropsheet">ComPropSheet</a> with a function code of <a href="print.cpsfunc_add_hpropsheetpage">CPSFUNC_ADD_HPROPSHEETPAGE</a>.)

</dd>
</dl>



### -field PSUIPAGEINSERT_PCOMPROPSHEETUI

CPSUI inserts pages described by a <a href="print.compropsheetui">COMPROPSHEETUI</a> structure.

(This is equivalent to calling <a href="print.compropsheet">ComPropSheet</a> with a function code of <a href="print.cpsfunc_add_pcompropsheetui">CPSFUNC_ADD_PCOMPROPSHEETUI</a>.)

</dd>
</dl>



### -field PSUIPAGEINSERT_PFNPROPSHEETUI

CPSUI calls the specified <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> typed function, with a reason value of PROPSHEETUI_REASON_INIT.

(This is equivalent to calling <a href="print.compropsheet">ComPropSheet</a> with a function code of <a href="print.cpsfunc_add_pfnpropsheetui">CPSFUNC_ADD_PFNPROPSHEETUI</a>.)

</dd>
</dl>



### -field PSUIPAGEINSERT_PROPSHEETPAGE

CPSUI inserts the page described by the specified PROPSHEETPAGE structure.

(This is equivalent to calling <a href="print.compropsheet">ComPropSheet</a> with a function code of <a href="print.cpsfunc_add_propsheetpage">CPSFUNC_ADD_PROPSHEETPAGE</a>.)

</dd>
</dl>

### -field Mode

Caller-supplied value indicating where CPSUI should insert the new pages. It must be one of the following values:




### -field INSPSUIPAGE_MODE_AFTER

CPSUI inserts pages after the page identified by the CPSUI page handle that is specified by the <i>lParam1</i> parameter to <a href="print.compropsheet">ComPropSheet</a>.

</dd>
</dl>



### -field INSPSUIPAGE_MODE_BEFORE

CPSUI inserts pages before the page identified by the CPSUI page handle that is specified by the <i>lParam1</i> parameter to <a href="print.compropsheet">ComPropSheet</a>.

</dd>
</dl>



### -field INSPSUIPAGE_MODE_FIRST_CHILD

CPSUI inserts pages as the first children of the parent group identified by the <i>hComPropSheet</i> parameter to <a href="print.compropsheet">ComPropSheet</a>.

The <i>lParam1</i> parameter to <a href="print.compropsheet">ComPropSheet</a> is ignored.

</dd>
</dl>



### -field INSPUIPAGE_MODE_INDEX

CPSUI inserts pages as children of the parent group identified by the <i>hComPropSheet</i> parameter to <a href="print.compropsheet">ComPropSheet</a>.

The <i>lParam1</i> parameter to <a href="print.compropsheet">ComPropSheet</a> specifies a zero-based index identifying where, within the set of children, the specified pages should be inserted. If <i>lParam1</i> is 0, the pages are inserted starting at page 1; if <i>lParam1</i> is 1, the pages are inserted starting at page 2; and so on. If the index is greater than the number of existing children, the new pages are added as the last children. The <i>lParam1</i> value must be specified as HINSPSUIPAGE_INDEX(index).

</dd>
</dl>



### -field INSPSUIPAGE_MODE_LAST_CHILD

CPSUI inserts pages as the last children of the parent group identified by the <i>hComPropSheet</i> parameter to <a href="print.compropsheet">ComPropSheet</a>.

The <i>lParam1</i> parameter to <a href="print.compropsheet">ComPropSheet</a> is ignored.

</dd>
</dl>

### -field dwData1


### -field dwData2


### -field dwData3

Caller-supplied values that depend on the contents of the <b>Type</b> member, as follows:




### -field PSUIPAGEINSERT_DLL

dwData1 - Caller-supplied pointer to a NULL-terminated string representing the DLL path name.

dwData2 - Caller-supplied pointer to a NULL-terminated string representing the name of a <a href="..\compstui\nc-compstui-pfnpropsheetui.md">PFNPROPSHEETUI</a> typed function, contained in the specified DLL.

dwData3 - Caller-supplied 32-bit value, passed to the PFNPROPSHEETUI-typed function for its <i>lParam</i> parameter.

</dd>
</dl>



### -field PSUIPAGEINSERT_GROUP_PARENT

dwData1 - Not used, must be zero.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.

</dd>
</dl>



### -field PSUIPAGEINSERT_HPROPSHEETPAGE

dwData1 - Caller-supplied handle to a property sheet, returned by <b>CreatePropertySheetPage</b>.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.

</dd>
</dl>



### -field PSUIPAGEINSERT_PCOMPROPSHEETUI

dwData1 - Caller-supplied pointer to a COMPROPSHEETUI structure.

dwData2 - On success, receives the number of pages inserted. On failure, receives an ERR_CPSUI-prefixed error code.

dwData3 - Not used, must be zero.

</dd>
</dl>



### -field PSUIPAGEINSERT_PFNPROPSHEETUI

dwData1 - Caller-supplied pointer to a PFNPROPSHEETUI-typed function.

dwData2 - Caller-supplied 32-bit value, passed to the PFNPROPSHEETUI-typed function for its <i>lParam</i> parameter.

dwData3 - Not used, must be zero.

</dd>
</dl>



### -field PSUIPAGEINSERT_PROPSHEETPAGE

dwData1 - Caller-supplied pointer to a PROPSHEETPAGE structure.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.

</dd>
</dl>

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