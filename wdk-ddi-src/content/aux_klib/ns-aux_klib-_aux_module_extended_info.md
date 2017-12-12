---
UID: NS.AUX_KLIB._AUX_MODULE_EXTENDED_INFO
title: _AUX_MODULE_EXTENDED_INFO
author: windows-driver-content
description: The AUX_MODULE_EXTENDED_INFO structure contains extended information about a loaded image module.
old-location: kernel\aux_module_extended_info.htm
old-project: kernel
ms.assetid: 9733b17d-c990-4eda-87e2-906f2f78c5d5
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _AUX_MODULE_EXTENDED_INFO, AUX_MODULE_EXTENDED_INFO, *PAUX_MODULE_EXTENDED_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AUX_MODULE_EXTENDED_INFO
req.alt-loc: aux_klib.h
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

# _AUX_MODULE_EXTENDED_INFO structure



## -description
The <b>AUX_MODULE_EXTENDED_INFO</b> structure contains extended information about a loaded image module.



## -syntax

````
typedef struct _AUX_MODULE_EXTENDED_INFO {
  AUX_MODULE_BASIC_INFO BasicInfo;
  ULONG                 ImageSize;
  USHORT                FileNameOffset;
  UCHAR                 FullPathName[AUX_KLIB_MODULE_PATH_LEN];
} AUX_MODULE_EXTENDED_INFO, *PAUX_MODULE_EXTENDED_INFO;
````


## -struct-fields

### -field BasicInfo

An <a href="kernel.aux_module_basic_info">AUX_MODULE_BASIC_INFO</a> structure.


### -field ImageSize

The size, in bytes, of the loaded image.


### -field FileNameOffset

The offset, in bytes, from the beginning of the full path name to the file name of the module's image file.


### -field FullPathName

The full path name of the module's image file.


## -remarks
The <b>AUX_MODULE_EXTENDED_INFO</b> structure is used as input to the <a href="kernel.auxklibquerymoduleinformation">AuxKlibQueryModuleInformation</a> routine. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Aux_klib.h (include Aux_klib.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.auxklibquerymoduleinformation">AuxKlibQueryModuleInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AUX_MODULE_EXTENDED_INFO structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

