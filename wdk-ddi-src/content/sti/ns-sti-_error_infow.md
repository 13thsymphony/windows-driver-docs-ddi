---
UID : NS:sti._ERROR_INFOW
title : _ERROR_INFOW
author : windows-driver-content
description : The STI_ERROR_INFO structure is used as a parameter for the IStiDevice::GetLastErrorInfo and IStiUSD::GetLastErrorInfo methods. It is also used as a member of the STI_DIAG structure.
old-location : image\sti_error_info.htm
old-project : image
ms.assetid : e448ddfc-ae5a-4eb8-a39c-e46771278081
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : _ERROR_INFOW, *PSTI_ERROR_INFOW, STI_ERROR_INFOW, *PSTI_ERROR_INFO, STI_ERROR_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : sti.h
req.include-header : Sti.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : STI_ERROR_INFO
req.alt-loc : sti.h
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
req.typenames : "*PSTI_ERROR_INFOW, STI_ERROR_INFOW"
req.product : Windows 10 or later.
---

# _ERROR_INFOW structure
The STI_ERROR_INFO structure is used as a parameter for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543749">IStiDevice::GetLastErrorInfo</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543820">IStiUSD::GetLastErrorInfo</a> methods. It is also used as a member of the <a href="..\sti\ns-sti-_sti_diag.md">STI_DIAG</a> structure.

## Syntax
````
typedef struct _ERROR_INFO {
  DWORD dwSize;
  DWORD dwGenericError;
  DWORD dwVendorError;
  WCHAR szExtendedErrorText[255];
} STI_ERROR_INFO, *PSTI_ERROR_INFO;
````

## Members

        
            `dwGenericError`

            Win32 error code.
        
            `dwSize`

            Caller-supplied size, in bytes, of the STI_ERROR_INFO structure.
        
            `dwVendorError`

            Optional, vendor-specific error code.
        
            `szExtendedErrorText`

            Optional character array containing a text string describing the error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sti.h (include Sti.h) |