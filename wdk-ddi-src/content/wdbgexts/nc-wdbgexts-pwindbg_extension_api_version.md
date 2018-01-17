---
UID: NC:wdbgexts.PWINDBG_EXTENSION_API_VERSION
title: PWINDBG_EXTENSION_API_VERSION
author: windows-driver-content
description: The PWINDBG_EXTENSION_API_VERSION (ExtensionApiVersion) callback function returns version information about the extension DLL.
old-location: debugger\extensionapiversion.htm
old-project: debugger
ms.assetid: 1bc24b16-7dbf-4c95-87ac-c9b38e6a4c59
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT, VPCI_WRITE_BLOCK_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdbgexts.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtensionApiVersion
req.alt-loc: wdbgexts.h
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
req.typenames: *PVPCI_WRITE_BLOCK_INPUT, VPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PWINDBG_EXTENSION_API_VERSION callback



## -description
The <i>PWINDBG_EXTENSION_API_VERSION</i> (<b>ExtensionApiVersion</b>) callback function returns version information about the extension DLL.



## -prototype

````
LPEXT_API_VERSION ExtensionApiVersion(void);
````


## -parameters


## -returns
This function must return a pointer to an <b>EXT_API_VERSION</b> structure.

This function must return a pointer to an <b>EXT_API_VERSION</b> structure.

This function must return a pointer to an <b>EXT_API_VERSION</b> structure.


## -remarks
You must define this function in your code using the prototype above. Include wdbgexts.h.

<i>ExtensionApiVersion</i> is called by the debugger when the extension DLL is loaded.

The debugger uses the <b>MajorVersion</b> and <b>MinorVersion</b> fields of the returned <b>EXT_API_VERSION</b> structure when executing commands like <a href="https://msdn.microsoft.com/73139b02-265a-424d-9de8-f4f3736e62db">.chain</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn973197">version</a> that display the extension version number. The debugger does not perform any "version checking" -- the extension DLL will be loaded regardless of what version numbers are present in these fields.

The <b>Revision</b> field of the returned <b>EXT_API_VERSION</b> structure should be EXT_API_VERSION_NUMBER64 if you are using 64-bit pointers in your code, or EXT_API_VERSION_NUMBER32 if you are using 32-bit pointers. It is recommended that you always use 64-bit pointers in your code, since the debugger will automatically resize these pointers when necessary. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

For more details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560220">Using WdbgExts Extension Callbacks</a>.</p>