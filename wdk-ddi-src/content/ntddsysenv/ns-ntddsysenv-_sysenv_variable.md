---
UID: NS.NTDDSYSENV._SYSENV_VARIABLE
title: _SYSENV_VARIABLE
author: windows-driver-content
description: Stores the name a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request.
old-location: kernel\sysenv_variable.htm
old-project: kernel
ms.assetid: 311A5977-C3F5-4287-B030-00F4BB9C8629
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SYSENV_VARIABLE, SYSENV_VARIABLE, PSYSENV_VARIABLE, *PSYSENV_VARIABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddsysenv.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SYSENV_VARIABLE
req.alt-loc: Ntddsysenv.h
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

# _SYSENV_VARIABLE structure



## -description
Stores the name a system environment variable using
    SysEnv device. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791526">IOCTL_SYSENV_GET_VARIABLE</a> request.



## -syntax

````
typedef struct _SYSENV_VARIABLE {
  GUID  VendorGuid;
  ULONG VariableNameLength;
  WCHAR VariableName[ANYSIZE_ARRAY];
} SYSENV_VARIABLE, *PSYSENV_VARIABLE;
````


## -struct-fields

### -field VendorGuid

The vendor GUID.


### -field VariableNameLength

The length of the string pointed to by  <b>VariableName</b>, which contains the name of the variable.


### -field VariableName

A string that  contains the name of the variable.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddsysenv.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt791526">IOCTL_SYSENV_GET_VARIABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SYSENV_VARIABLE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

