---
UID: NS:wdm._REG_POST_CREATE_KEY_INFORMATION
title: _REG_POST_CREATE_KEY_INFORMATION
author: windows-driver-content
description: The REG_POST_CREATE_KEY_INFORMATION structure contains the result of an attempt to create a registry key.
old-location: kernel\reg_post_create_key_information.htm
old-project: kernel
ms.assetid: bba965c9-7132-4988-bf89-b19004118c0a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _REG_POST_CREATE_KEY_INFORMATION, *PREG_POST_OPEN_KEY_INFORMATION, REG_POST_OPEN_KEY_INFORMATION, *PREG_POST_CREATE_KEY_INFORMATION, REG_POST_CREATE_KEY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available only on Microsoft Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_POST_CREATE_KEY_INFORMATION
req.alt-loc: Wdm.h
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
req.typenames: *PREG_POST_OPEN_KEY_INFORMATION, REG_POST_OPEN_KEY_INFORMATION, *PREG_POST_CREATE_KEY_INFORMATION, REG_POST_CREATE_KEY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_POST_CREATE_KEY_INFORMATION structure



## -description
The <b>REG_POST_CREATE_KEY_INFORMATION</b> structure contains the result of an attempt to create a registry key.



## -syntax

````
typedef struct _REG_POST_CREATE_KEY_INFORMATION {
  PUNICODE_STRING CompleteName;
  PVOID           Object;
  NTSTATUS        Status;
} REG_POST_CREATE_KEY_INFORMATION, REG_POST_OPEN_KEY_INFORMATION, *PREG_POST_CREATE_KEY_INFORMATION;
````


## -struct-fields

### -field CompleteName

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that specifies the complete path of the registry key. 


### -field Object

A pointer to the registry key object that was created.


### -field Status

The NTSTATUS value that the system will return for the registry operation.


## -remarks
For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available only on Microsoft Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_POST_CREATE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

