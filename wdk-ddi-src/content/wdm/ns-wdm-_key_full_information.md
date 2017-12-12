---
UID: NS.WDM._KEY_FULL_INFORMATION
title: _KEY_FULL_INFORMATION
author: windows-driver-content
description: The KEY_FULL_INFORMATION structure defines the information available for a registry key, including information about its subkeys and the maximum length for their names and value entries.
old-location: kernel\key_full_information.htm
old-project: kernel
ms.assetid: dd099435-e3e3-4d78-a829-0f12f2db46d9
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _KEY_FULL_INFORMATION, KEY_FULL_INFORMATION, *PKEY_FULL_INFORMATION
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
req.alt-api: KEY_FULL_INFORMATION
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

# _KEY_FULL_INFORMATION structure



## -description
The <b>KEY_FULL_INFORMATION</b> structure defines the information available for a registry key, including information about its subkeys and the maximum length for their names and value entries. This information can be used to size buffers to get the names of subkeys and their value entries.



## -syntax

````
typedef struct _KEY_FULL_INFORMATION {
  LARGE_INTEGER LastWriteTime;
  ULONG         TitleIndex;
  ULONG         ClassOffset;
  ULONG         ClassLength;
  ULONG         SubKeys;
  ULONG         MaxNameLen;
  ULONG         MaxClassLen;
  ULONG         Values;
  ULONG         MaxValueNameLen;
  ULONG         MaxValueDataLen;
  WCHAR         Class[1];
} KEY_FULL_INFORMATION, *PKEY_FULL_INFORMATION;
````


## -struct-fields

### -field LastWriteTime

The last time this key or any of its values changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.


### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field ClassOffset

The byte offset from the start of this structure to the <b>Class</b> member.


### -field ClassLength

The size, in bytes, of the key class name string in the <b>Class</b> array.


### -field SubKeys

The number of subkeys for this key.


### -field MaxNameLen

The maximum size, in bytes, of any name for a subkey.


### -field MaxClassLen

The maximum size, in bytes, of a class name.


### -field Values

The number of value entries for this key.


### -field MaxValueNameLen

The maximum size, in bytes, of a value entry name.


### -field MaxValueDataLen

The maximum size, in bytes, of a value entry data field.


### -field Class

An array of wide characters that contains the name of the class of the key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_FULL_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks
The <a href="kernel.zwenumeratekey">ZwEnumerateKey</a> and <a href="kernel.zwquerykey">ZwQueryKey</a> routines use the <b>KEY_FULL_INFORMATION</b> structure to contain the full information for a registry key. When the <i>KeyInformationClass</i> parameter of either routine is <b>KeyFullInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_FULL_INFORMATION</b> structure.  For more information about the <b>KeyFullInformation</b> enumeration value, see <a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a>.


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
<a href="kernel.key_basic_information">KEY_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_cached_information">KEY_CACHED_INFORMATION</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_FULL_INFORMATION structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

