---
UID: NS:winsplp.MESSAGEBOX_PARAMS
title: MESSAGEBOX_PARAMS
author: windows-driver-content
description: The MESSAGEBOX_PARAMS structure is used by the SplPromptUIInUsersSession function to hold information about the appearance and behavior of a message box.
old-location: print\messagebox_params.htm
old-project: print
ms.assetid: 28a94e25-9beb-46a1-9e9d-9fe4823372be
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMESSAGEBOX_PARAMS, MESSAGEBOX_PARAMS, MESSAGEBOX_PARAMS structure [Print Devices], PMESSAGEBOX_PARAMS, PMESSAGEBOX_PARAMS structure pointer [Print Devices], print.messagebox_params, spoolfnc_c70908b4-e8de-4e3e-810d-d76cf2104d91.xml, winsplp/MESSAGEBOX_PARAMS, winsplp/PMESSAGEBOX_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	MESSAGEBOX_PARAMS
product: Windows
targetos: Windows
req.typenames: MESSAGEBOX_PARAMS, *PMESSAGEBOX_PARAMS
req.product: Windows 10 or later.
---

# MESSAGEBOX_PARAMS structure
The MESSAGEBOX_PARAMS structure is used by the <a href="..\winsplp\nf-winsplp-splpromptuiinuserssession.md">SplPromptUIInUsersSession</a> function to hold information about the appearance and behavior of a message box.

## Syntax
````
typedef struct {
  DWORD  cbSize;
  LPWSTR pTitle;
  LPWSTR pMessage;
  DWORD  Style;
  DWORD  dwTimeout;
  BOOL   bWait;
} MESSAGEBOX_PARAMS, *PMESSAGEBOX_PARAMS;
````

## Members


`bWait`

Specifies whether the <b>SplPromptUIInUsersSession</b> function should wait for a user's response. If <b>bWait</b> is <b>TRUE</b>, <b>SplPromptUIInUsersSession</b> does not return until either the user responds or the time-out interval elapses. If <b>dwTimeout</b> is zero, <b>SplPromptUIInUsersSession</b> does not return until the user responds. If <b>bWait</b> is <b>FALSE</b>, the function returns immediately with *<i>pResponse</i> set to IDASYNC.

`cbSize`

Specifies the size, in bytes, of this structure.

`dwTimeout`

Specifies the time, in seconds, to wait for the user's response, provided that the <b>bWait</b> member is <b>TRUE</b>.

`pMessage`

Pointer to a null-terminated string that contains the message to display.

`pTitle`

Pointer to a null-terminated string that is used in the title bar of the message box.

`Style`

Specifies the contents and behavior of the message box. For a complete list of the values to which this member can be set, see the description of the <b>MessageBox</b> function in the Microsoft Windows SDK documentation.

## Remarks
One member of the <a href="..\winsplp\ns-winsplp-showuiparams.md">SHOWUIPARAMS</a> structure is a MESSAGEBOX_PARAMS structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure is available in Windows XP and later operating systems. This structure is available in Windows XP and later operating systems. |
| **Header** | winsplp.h (include Winsplp.h) |

## See Also

<a href="..\winsplp\nf-winsplp-splpromptuiinuserssession.md">SplPromptUIInUsersSession</a>



<a href="..\winsplp\ns-winsplp-showuiparams.md">SHOWUIPARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MESSAGEBOX_PARAMS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>