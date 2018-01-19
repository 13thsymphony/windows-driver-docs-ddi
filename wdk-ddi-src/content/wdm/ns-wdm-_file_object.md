---
UID : NS:wdm._FILE_OBJECT
title : _FILE_OBJECT
author : windows-driver-content
description : The Common Log File System (CLFS) uses the LOG_FILE_OBJECT structure to represent logs.
old-location : kernel\log_file_object.htm
old-project : kernel
ms.assetid : 6eefdbbb-59de-4cc8-a309-8353a05cba41
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _FILE_OBJECT, *PFILE_OBJECT, FILE_OBJECT, *PLOG_FILE_OBJECT, LOG_FILE_OBJECT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : LOG_FILE_OBJECT
req.alt-loc : Wdm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL (see Remarks section)
req.typenames : "*PFILE_OBJECT, FILE_OBJECT"
req.product : Windows 10 or later.
---

# _FILE_OBJECT structure
The Common Log File System (CLFS) uses the <b>LOG_FILE_OBJECT</b> structure to represent logs. The <a href="..\wdm\nf-wdm-clfscreatelogfile.md">ClfsCreateLogFile</a> function returns a pointer to a <b>LOG_FILE_OBJECT</b> structure, which clients then pass to other CLFS functions.

## Syntax
````
typedef FILE_OBJECT LOG_FILE_OBJECT, *PLOG_FILE_OBJECT, **PPLOG_FILE_OBJECT;
````

## Members


    ## Remarks
        CLFS clients do not directly access the members of a <b>LOG_FILE_OBJECT</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20LOG_FILE_OBJECT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>