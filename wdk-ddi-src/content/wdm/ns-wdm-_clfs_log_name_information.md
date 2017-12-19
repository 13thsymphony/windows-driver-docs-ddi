---
UID: NS.WDM._CLFS_LOG_NAME_INFORMATION
title: _CLFS_LOG_NAME_INFORMATION
author: windows-driver-content
description: The CLFS_LOG_NAME_INFORMATION structure holds the name of a Common Log File System (CLFS) stream or log.
old-location: kernel\clfs_log_name_information.htm
old-project: kernel
ms.assetid: 6011a3e9-1de1-4862-b6a4-a3becf3ec3ca
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _CLFS_LOG_NAME_INFORMATION, CLFS_LOG_NAME_INFORMATION, PPCLFS_LOG_NAME_INFORMATION, *PCLFS_LOG_NAME_INFORMATION, PCLFS_LOG_NAME_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CLFS_LOG_NAME_INFORMATION
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _CLFS_LOG_NAME_INFORMATION structure



## -description
The <b>CLFS_LOG_NAME_INFORMATION</b> structure holds the name of a Common Log File System (CLFS) stream or log.



## -syntax

````
typedef struct _CLFS_LOG_NAME_INFORMATION {
  USHORT NameLengthInBytes;
  WCHAR  Name[1];
} CLFS_LOG_NAME_INFORMATION, *PCLFS_LOG_NAME_INFORMATION, **PPCLFS_LOG_NAME_INFORMATION;
````


## -struct-fields

### -field NameLengthInBytes

The size, in bytes, of the log name.


### -field Name

An array of wide characters that holds the log name. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.clfssetlogfileinformation">ClfsSetLogFileInformation</a>
</dt>
<dt>
<a href="kernel.clfsquerylogfileinformation">ClfsQueryLogFileInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_LOG_NAME_INFORMATION structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

