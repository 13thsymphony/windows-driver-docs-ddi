---
UID: NS:wiamicro.VAL
title: VAL
author: windows-driver-content
description: The VAL structure is used by the microdriver and WIA Flatbed driver to pass information between each other.
old-location: image\val.htm
old-project: image
ms.assetid: 9c9cf520-3249-4c1e-9d0d-e07f7127117e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.val, wiamicro/PVAL, MicroDrv_397b66fc-2f8e-434e-88ac-24b5cdd415d5.xml, VAL, wiamicro/VAL, PVAL structure pointer [Imaging Devices], PVAL, *PVAL, VAL structure [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	wiamicro.h
apiname:
-	VAL
product: Windows
targetos: Windows
req.typenames: VAL, *PVAL
req.product: Windows 10 or later.
---

# VAL structure
The VAL structure is used by the microdriver and WIA Flatbed driver to pass information between each other.

## Syntax
````
typedef struct VAL {
  LONG      lVal;
  double    dblVal;
  GUID      *pGuid;
  PSCANINFO pScanInfo;
  HGLOBAL   handle;
  WCHAR     **ppButtonNames;
  HANDLE    *pHandle;
  LONG      lReserved;
  CHAR      szVal[MAX_ANSI_CHAR];
} VAL, *PVAL;
````

## Members


`dblVal`

Specifies a command value to return to the WIA Flatbed driver. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552714">WIA Microdriver Commands</a> for a list of available commands for this parameter.

`handle`

Points to a ShutDown event handle that will be signaled by the WIA Flatbed Driver when the driver is being unloaded or shut down.

`lReserved`

Reserved. Do not use.

`lVal`

Specifies a command value to return to the WIA Flatbed driver. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff552714">WIA Microdriver Commands</a> for a list of available commands for this parameter.

`pGuid`

Points to the GUID of the pressed button. If no button was pressed, this member points to GUID_NULL.

`pHandle`

Points to an event handle.

`ppButtonNames`

Specifies the address of a pointer to an array of button names.

`pScanInfo`

Points to a <a href="..\wiamicro\ns-wiamicro-_scaninfo.md">SCANINFO</a> structure.

`szVal`

Specifies the device name in ASCII form. If needed for interrupt checking, the microdriver can use this name to pass to <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> (described in the Microsoft Windows SDK documentation) in order to obtain a file handle to the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems. Available in Windows Me and in Windows XP and later versions of the Windows operating systems. |
| **Header** | wiamicro.h (include Wiamicro.h) |