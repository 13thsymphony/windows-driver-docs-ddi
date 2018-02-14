---
UID: NS:winsplp.SHOWUIPARAMS
title: SHOWUIPARAMS
author: windows-driver-content
description: The SplPromptUIInUsersSession function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box.
old-location: print\showuiparams.htm
old-project: print
ms.assetid: 63ee7f5c-ca95-4c2d-be17-56a769188f8c
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: PSHOWUIPARAMS, winsplp/PSHOWUIPARAMS, SHOWUIPARAMS, winsplp/SHOWUIPARAMS, PSHOWUIPARAMS structure pointer [Print Devices], spoolfnc_bf6ce7c8-8b86-40c9-9b03-64c3e3366a04.xml, *PSHOWUIPARAMS, print.showuiparams, SHOWUIPARAMS structure [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: This function is available in Windows XP and later operating systems.
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
-	winsplp.h
apiname:
-	SHOWUIPARAMS
product: Windows
targetos: Windows
req.typenames: "*PSHOWUIPARAMS, SHOWUIPARAMS"
req.product: Windows 10 or later.
---

# SHOWUIPARAMS structure
The <a href="..\winsplp\nf-winsplp-splpromptuiinuserssession.md">SplPromptUIInUsersSession</a> function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box.

## Syntax
````
typedef struct {
  UI_TYPE           UIType;
  MESSAGEBOX_PARAMS MessageBoxParams;
} SHOWUIPARAMS, *PSHOWUIPARAMS;
````

## Members


`MessageBoxParams`

Specifies a <a href="..\winsplp\ns-winsplp-messagebox_params.md">MESSAGEBOX_PARAMS</a> structure that contains the information about the message box.

`UIType`

Specifies the type of user interface element. This member can be set to a single value: <b>kMessageBox</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This function is available in Windows XP and later operating systems. This function is available in Windows XP and later operating systems. |
| **Header** | winsplp.h (include Winsplp.h) |

## See Also

<a href="..\winsplp\nf-winsplp-splpromptuiinuserssession.md">SplPromptUIInUsersSession</a>



<a href="..\winsplp\ns-winsplp-messagebox_params.md">MESSAGEBOX_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20SHOWUIPARAMS structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>