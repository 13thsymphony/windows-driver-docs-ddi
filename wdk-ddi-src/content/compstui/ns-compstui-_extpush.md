---
UID : NS:compstui._EXTPUSH
title : "_EXTPUSH"
author : windows-driver-content
description : The EXTPUSH structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed.
old-location : print\extpush.htm
old-project : print
ms.assetid : c38d7eca-6486-4bb1-b0a8-7f69fe13f7db
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : EXTPUSH structure [Print Devices], _EXTPUSH, compstui/EXTPUSH, PEXTPUSH, *PEXTPUSH, EXTPUSH, cpsuifnc_d8f5e9ba-ef61-4adb-959f-1d0ebf456dad.xml, print.extpush, compstui/PEXTPUSH, PEXTPUSH structure pointer [Print Devices]
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
req.typenames : "*PEXTPUSH, EXTPUSH"
---

# _EXTPUSH structure
The EXTPUSH structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed.

## Syntax
````
typedef struct _EXTPUSH {
  WORD      cbSize;
  WORD      Flags;
  LPTSTR    pTitle;
  union {
    DLGPROC DlgProc;
    FARPROC pfnCallBack;
  };
  ULONG_PTR IconID;
  union {
    WORD   DlgTemplateID;
    HANDLE hDlgTemplate;
  };
  ULONG_PTR dwReserved[3];
} EXTPUSH, *PEXTPUSH;
````

## Members


`cbSize`

Size, in bytes, of the EXTPUSH structure.

`dwReserved`

Reserved, must be initialized to zero.

`Flags`

Bit flags, which can be one of the following:


















#### EPF_ICONID_AS_HICON

If set, the <b>IconID</b> member contains an icon handle.

If not set, the <b>IconID</b> member contains an icon resource identifier.


#### EPF_INCLUDE_SETUP_TITLE

If set, CPSUI appends "Setup" to the string pointed to by <b>pTitle</b>.


#### EPF_NO_DOT_DOT_DOT

If set, CPSUI does not append "..." to the string pointed to by <b>pTitle</b>.


#### EPF_OVERLAY_NO_ICON

If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the <b>IconID</b> member.


#### EPF_OVERLAY_STOP_ICON

If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the <b>IconID</b> member.


#### EPF_OVERLAY_WARNING_ICON

If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the <b>IconID</b> member.


#### EPF_PUSH_TYPE_DLGPROC

If set, the <b>DlgProc</b> and <b>DlgTemplateID/hDlgTemplate</b> members are valid.

If not set, the <b>pfnCallBack</b> member is valid.


#### EPF_USE_HDLGTEMPLATE

If set, <b>hDlgTemplate</b> contains a template handle.

If not set, <b>DlgTemplateID</b> contains a template resource identifier.

`IconID`

One of the following icon identifiers:
<ul>
<li>
An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

</li>
<li>
An icon handle. If a handle is specified, EPF_ICONID_AS_HICON must be set in the <b>Flags</b> member.

</li>
</ul>CPSUI displays the icon next to the push button. If this value is zero, an icon is not displayed.

`pTitle`

String identifier, representing the push button title. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.

## Remarks
An extended push button is a CPSUI-defined type of push button that can be associated with an <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure. An OPTITEM structure can have one extended push button or one extended check box associated with it.

When you use the EXTPUSH structure to create a push button, you can optionally create an additional dialog box that opens when the user clicks on the button. To create this dialog box, you should specify a pointer to a dialog box procedure in the <b>DlgProc</b> member, and include a dialog template specification in either the <b>DlgTemplateID</b> or the <b>hDlgTemplate</b> member.

If EPF_USE_HDLGTEMPLATE is set in <b>Flags</b>, CPSUI creates the dialog box by calling <b>DialogBoxIndirectParam</b> (described in the Windows SDK documentation), passing the contents of the <b>DlgProc</b> and <b>hDlgTemplate</b> members.

If EPF_USE_HDLGTEMPLATE is not set in <b>Flags</b>, CPSUI creates the dialog box by calling <b>DialogBoxParam</b> (described in the Windows SDK documentation), passing the contents of the <b>DlgProc</b> and <b>DlgTemplateID</b> members.

When the dialog box procedure is called with a <i>uMsg</i> value of WM_INITDIALOG, the <i>lParam</i> value is the address of a <a href="..\compstui\ns-compstui-_cpsuicbparam.md">CPSUICBPARAM</a> structure, with the <b>Reason</b> member set to CPSUICB_REASON_EXTPUSH. (For more information about the <i>uMsg</i> and <i>lParam</i> parameters, see <b>DialogProc</b> in the Windows SDK documentation.)

If you do not need CPSUI to display a dialog box when the user clicks on the button, you can specify the address of a <a href="..\compstui\nc-compstui-_cpsuicallback.md">_CPSUICALLBACK</a>-typed callback function in the <b>pfnCallBack</b> member. When a user clicks on the button, CPSUI calls the callback function. The accompanying CPSUICBPARAM structure's <b>Reason</b> member will be set to CPSUICB_REASON_EXTPUSH.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | compstui.h (include Compstui.h) |

## See Also

<a href="..\compstui\ns-compstui-_extchkbox.md">EXTCHKBOX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20EXTPUSH structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>