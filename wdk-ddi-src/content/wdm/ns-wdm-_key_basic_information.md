---
UID: NS.WDM._KEY_BASIC_INFORMATION
title: _KEY_BASIC_INFORMATION
author: windows-driver-content
description: The KEY_BASIC_INFORMATION structure defines a subset of the full information that is available for a registry key.
old-location: kernel\key_basic_information.htm
old-project: kernel
ms.assetid: 789c60b6-a5a4-4570-bb0c-acfe1166a302
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _KEY_BASIC_INFORMATION, KEY_BASIC_INFORMATION, PKEY_BASIC_INFORMATION, *PKEY_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEY_BASIC_INFORMATION
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
req.product: Windows 10 or later.
---

# _KEY_BASIC_INFORMATION structure



## -description
The <b>KEY_BASIC_INFORMATION</b> structure defines a subset of the full information that is available for a registry key.



## -syntax

````
typedef struct _KEY_BASIC_INFORMATION {
  LARGE_INTEGER LastWriteTime;
  ULONG         TitleIndex;
  ULONG         NameLength;
  WCHAR         Name[1];
} KEY_BASIC_INFORMATION, *PKEY_BASIC_INFORMATION;
````


## -struct-fields

### -field LastWriteTime

The last time this key or any of its values changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.


### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field NameLength

The size, in bytes, of the key name string in the <b>Name</b> array.


### -field Name

An array of wide characters that contains the name of the registry key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_BASIC_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks
The <a href="kernel.zwenumeratekey">ZwEnumerateKey</a> and <a href="kernel.zwquerykey">ZwQueryKey</a> routines use the <b>KEY_BASIC_INFORMATION</b> structure to contain the basic information for a registry key. When the <i>KeyInformationClass</i> parameter of either routine is <b>KeyBasicInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_BASIC_INFORMATION</b> structure.  For more information about the <b>KeyBasicInformation</b> enumeration value, see <a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a>.


## -requirements
<table>
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
<a href="kernel.key_cached_information">KEY_CACHED_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_full_information">KEY_FULL_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.key_name_information">KEY_NAME_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_node_information">KEY_NODE_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_virtualization_information">KEY_VIRTUALIZATION_INFORMATION</a>
</dt>
<dt>
<a href="kernel.zwenumeratekey">ZwEnumerateKey</a>
</dt>
<dt>
<a href="kernel.zwquerykey">ZwQueryKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_BASIC_INFORMATION structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

