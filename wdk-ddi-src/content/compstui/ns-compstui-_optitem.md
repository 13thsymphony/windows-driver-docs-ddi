---
UID : NS:compstui._OPTITEM
title : _OPTITEM
author : windows-driver-content
description : The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one property sheet option on a property sheet page, if the page is described by a COMPROPSHEETUI structure.
old-location : print\optitem.htm
old-project : print
ms.assetid : 983f9774-d498-473a-bdfb-ec55cc4298cf
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : _OPTITEM, *POPTITEM, OPTITEM
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
req.alt-api : OPTITEM
req.alt-loc : compstui.h
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
req.typenames : "*POPTITEM, OPTITEM"
---

# _OPTITEM structure
The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one <a href="https://msdn.microsoft.com/572330d6-1a1b-46fd-bfb4-be2b0990bca4">property sheet option</a> on a property sheet page, if the page is described by a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.

## Syntax
````
typedef struct _OPTITEM {
  WORD      cbSize;
  BYTE      Level;
  BYTE      DlgPageIdx;
  DWORD     Flags;
  ULONG_PTR UserData;
  LPTSTR    pName;
  union {
    LONG   Sel;
    LPTSTR pSel;
  };
  union {
    PEXTCHKBOX pExtChkBox;
    PEXTPUSH   pExtPush;
  };
  POPTTYPE  pOptType;
  DWORD     HelpIndex;
  BYTE      DMPubID;
  BYTE      UserItemID;
  WORD      wReserved;
  POIEXT    pOIExt;
  ULONG_PTR dwReserved[3];
} OPTITEM, *POPTITEM;
````

## Members

        
            `cbSize`

            Size, in bytes, of the OPTITEM structure.
        
            `DlgPageIdx`

            Identifies the dialog to which the option belongs. Specifies an array index into the DLGPAGE array pointed to by the <b>pDlgPage</b> member of the <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.

If <b>pDlgPage</b> points to a CPSUI-supplied, predefined DLGPAGE structure, CPSUI supplies this index.
        
            `DMPubID`

            This member is meant for use by printer interface DLLs, when creating a <b>Document Properties</b> property sheet (see <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>). It is a constant value specifying which, if any, public member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure is associated with this option. The following table lists available constants, the associated DEVMODE structure member, and the required value for <b>pName</b> for each constant.

<table>
<tr>
<th rowspan="2">Constant Value</th>
<th>Public DEVMODE</th>
<th rowspan="2">Required pName Value</th>
</tr>
<tr>
<th>Structure Member</th>
</tr>
<tr>
<td>
DMPUB_COLOR

</td>
<td>
<b>dmColor</b>

</td>
<td>
IDS_CPSUI_COLOR_APPERANCE

</td>
</tr>
<tr>
<td>
DMPUB_COPIES_COLLATE

</td>
<td>
<b>dmCopies</b> and <b>dmCollate</b>

</td>
<td>
IDS_CPSUI_COPIES

</td>
</tr>
<tr>
<td>
DMPUB_DEFSOURCE

</td>
<td>
<b>dmDefSource</b>

</td>
<td>
IDS_CPSUI_SOURCE

</td>
</tr>
<tr>
<td>
DMPUB_DITHERTYPE

</td>
<td>
<b>dmDitherType</b>

</td>
<td>
IDS_CPSUI_DITHERING

</td>
</tr>
<tr>
<td>
DMPUB_DUPLEX

</td>
<td>
<b>dmDuplex</b>

</td>
<td>
IDS_CPSUI_DUPLEX

</td>
</tr>
<tr>
<td>
DMPUB_FORMNAME

</td>
<td>
<b>dmFormName</b>

</td>
<td>
IDS_CPSUI_FORMNAME

</td>
</tr>
<tr>
<td>
DMPUB_ICMINTENT

</td>
<td>
<b>dmICMIntent</b>

</td>
<td>
IDS_CPSUI_ICMINTENT

</td>
</tr>
<tr>
<td>
DMPUB_ICMMETHOD

</td>
<td>
<b>dmICMMethod</b>

</td>
<td>
IDS_CPSUI_ICMMETHOD

</td>
</tr>
<tr>
<td>
DMPUB_MEDIATYPE

</td>
<td>
<b>dmMediaType</b>

</td>
<td>
IDS_CPSUI_MEDIA

</td>
</tr>
<tr>
<td>
DMPUB_NUP

</td>
<td>
Not contained in public section of DEVMODE.

</td>
<td>
IDS_CPSUI_NUP

</td>
</tr>
<tr>
<td>
DMPUB_ORIENTATION

</td>
<td>
<b>dmOrientation</b>

</td>
<td>
IDS_CPSUI_ORIENTATION

</td>
</tr>
<tr>
<td>
DMPUB_OUTPUTBIN

</td>
<td>
Not contained in public section of DEVMODE.

</td>
<td>
IDS_CPSUI_OUTPUTBIN

</td>
</tr>
<tr>
<td>
DMPUB_PAGEORDER

</td>
<td>
Not contained in public section of DEVMODE.

</td>
<td>
IDS_CPSUI_PAGEORDER

</td>
</tr>
<tr>
<td>
DMPUB_PRINTQUALITY

</td>
<td>
<b>dmPrintQuality</b>

</td>
<td>
IDS_CPSUI_PRINTQUALITY or IDS_CPSUI_RESOLUTION.

If not specified, the default name is IDS_CPSUI_RESOLUTION.

</td>
</tr>
<tr>
<td>
DMPUB_QUALITY

</td>
<td>
Not contained in public section of DEVMODE.

</td>
<td>
IDS_CPSUI_QUALITY_SETTINGS

</td>
</tr>
<tr>
<td>
DMPUB_SCALE

</td>
<td>
<b>dmScale</b>

</td>
<td>
IDS_CPSUI_SCALE

</td>
</tr>
<tr>
<td>
DMPUB_TTOPTION

</td>
<td>
<b>dmTTOption</b>

</td>
<td>
IDS_CPSUI_TTOPTION

</td>
</tr>
<tr>
<td>
DMPUB_NONE

</td>
<td>
Not contained in public section of DEVMODE.

</td>
<td></td>
</tr>
<tr>
<td>
Greater than or equal to DMPUB_USER

</td>
<td>
Ignored by CPSUI, can be a caller-defined value.

</td>
<td></td>
</tr>
</table>
 

CPSUI does not maintain a DEVMODE structure. The application is responsible for copying user-selected option parameters into a DEVMODE structure. CPSUI uses <b>DMPubID</b> contents to determine treeview placement of standard options, and to determine the contents of the <b>Layout</b> and <b>Paper/Quality</b> tabs (see the <b>pDlgPage</b> member of the <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure).

For additional information about using the <b>DMPubID</b> member, see the following Remarks section.
        
            `dwReserved`

            Reserved, must be initialized to zero.
        
            `Flags`

            Optional bit flags that modify the option's characteristics. The OPTIF_CHANGEONCE flag is set by CPSUI; all other flags are set by the caller. Any combination of the following flags can be set.
        
            `HelpIndex`

            Help file index, which identifies help text to be associated with the option. If zero, help file text does not exist for this option. Note that the <b>pOIExt</b> member of this structure must be set with the address of an <a href="..\compstui\ns-compstui-_oiext.md">OIEXT</a> structure in order for help text functionality to exist.
        
            `Level`

            Specifies the level of this option in the treeview. For more information, see the following Remarks section.
        
            `pName`

            String identifier representing a localized, displayable option name. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier, with HIWORD set to zero. (Also see the description of <b>DMPubID</b>, below.)
        
            `pOIExt`

            Pointer to an optional <a href="..\compstui\ns-compstui-_oiext.md">OIEXT</a> structure. The caller is responsible for allocating storage for this structure.
        
            `pOptType`

            Pointer to an <a href="..\compstui\ns-compstui-_opttype.md">OPTTYPE</a> structure that describes the option's display type. If <b>NULL</b>, the option has no parameters and is used as a parent to options with a higher <b>Level</b> value. The child options must immediately follow the parent in the OPTITEM array. (See the following Remarks section.)
        
            `UserData`

            Optional 32-bit value that can be set and used by the caller.

(Printer interface DLLs for <a href="wdkgloss.u#wdkgloss.unidrv#wdkgloss.unidrv"><i>Unidrv</i></a> and <a href="wdkgloss.p#wdkgloss.pscript#wdkgloss.pscript"><i>Pscript</i></a> use this member to supply a pointer to a <a href="..\printoem\ns-printoem-_userdata.md">USERDATA</a> structure. <a href="https://msdn.microsoft.com/22ac2af6-37d8-4913-95af-9c3dc8576d40">User interface plug-ins</a> can reference this structure.)
        
            `UserItemID`

            Optional application-supplied value that can be used for option identification purposes. Not referenced by CPSUI.
        
            `wReserved`

            Reserved, must be initialized to zero.

    ## Remarks
        OPTITEM structures should be placed in an array, and the array's address should be placed in the <b>pOptItem</b> member of a <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> structure.

The <b>Level</b> member allows you to create child nodes in the treeview. For example, to create a set of option nodes under a level 1 parent node, specify level 2 for each child node and include their OPTITEM structures in the OPTITEM array, immediately after the parent's OPTITEM structure. In the parent's OPTITEM structure, <b>pOptType</b> should be <b>NULL</b>. 

The treeview root node is level 0. Options displayed when a user expands the root node are level 1. The maximum number of levels is 256.

For option values that are stored in a printer's DEVMODE structure, the <b>DMPubID</b> member must identify the option. For each <b>DMPubID</b> value that is used, a printer interface DLL must specify the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a> listed in the following table.

DMPUB_COLOR


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562825">TVOT_2STATES</a>


DMPUB_COPIES_COLLATE


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562853">TVOT_UDARROW</a> plus <a href="..\compstui\ns-compstui-_extchkbox.md">EXTCHKBOX</a> (See comments following this table.)

DMPUB_DEFSOURCE


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562839">TVOT_LISTBOX</a>


DMPUB_DITHERTYPE

DMPUB_DUPLEX


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562825">TVOT_2STATES</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562827">TVOT_3STATES</a>


DMPUB_FORMNAME

DMPUB_ICMINTENT

DMPUB_ICMMETHOD

DMPUB_MEDIATYPE

DMPUB_NUP

DMPUB_ORIENTATION

DMPUB_OUTPUTBIN

DMPUB_PAGEORDER

DMPUB_PRINTQUALITY

DMPUB_QUALITY

DMPUB_SCALE


<a href="https://msdn.microsoft.com/library/windows/hardware/ff562853">TVOT_UDARROW</a>


DMPUB_TTOPTION

If <b>DMPubID</b> is DMPUB_COPIES_COLLATE and the printer can collate copies, an extended check box (EXTCHKBOX structure) must be provided. The EXTCHCKBOX structure's members must be set as follows:

If OPTIF_EXT_HIDE is not set in <b>Flags</b>, CPSUI enables the check box if a user requests more than one copy, and disables it if only one copy is requested.

Additionally, CPSUI sets the option's display text to <b>copy</b> for one copy and <b>copies</b> for more than one copy.

If <b>DMPubID</b> is DMPUB_COLOR, its first <a href="..\compstui\ns-compstui-_optparam.md">OPTPARAM</a> structure (<b>Sel</b>=0) must represent Gray Scale, and <b>pData</b> in the OPTPARAM structure must be IDS_CPSUI_GRAYSCALE. Its second OPTPARAM structure (<b>Sel</b>=1) must represent Color, and <b>pData</b> in the OPTPARAM structure must be IDS_CPSUI_COLOR. If another option's <b>DMPubID</b> is DMPUB_ICMINTENT and if Color is not selected, CPSUI disables the option for which DMPUB_ICMINTENT is specified.

CPSUI disables color matching when Color is not selected.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | compstui.h (include Compstui.h) |