---
UID: NS.wdm._REG_SAVE_KEY_INFORMATION
title: REG_SAVE_KEY_INFORMATION
author: windows-driver-content
description: The REG_SAVE_KEY_INFORMATION structure contains the information for a registry key that is about to be saved.
old-location: kernel\reg_save_key_information.htm
old-project: kernel
ms.assetid: 911e1035-4415-43c1-9e9c-cc8feab2bd97
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: REG_SAVE_KEY_INFORMATION, REG_SAVE_KEY_INFORMATION, *PREG_SAVE_KEY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista SP2.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_SAVE_KEY_INFORMATION
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
req.iface: 
req.product: Windows 10 or later.
---

# REG_SAVE_KEY_INFORMATION structure



## -description
<p>The <b>REG_SAVE_KEY_INFORMATION</b> structure contains the information for a registry key that is about to be saved.</p>


## -syntax

````
typedef struct _REG_SAVE_KEY_INFORMATION {
  PVOID  Object;
  HANDLE FileHandle;
  ULONG  Format;
  PVOID  CallContext;
  PVOID  ObjectContext;
  PVOID  Reserved;
} REG_SAVE_KEY_INFORMATION, *PREG_SAVE_KEY_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>Object</b>

<dd>
<p>A pointer to a registry key object for the key whose information is about to be saved.</p>
</dd>

### -field <b>FileHandle</b>

<dd>
<p>A handle to the file to which the hive information will be saved.</p>
</dd>

### -field <b>Format</b>

<dd>
<p>The format in which the key or hive is saved. This member can have one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>REG_STANDARD_FORMAT</td>
<td>Save in standard format. The standard format is the only format supported by Windows 2000.</td>
</tr>
<tr>
<td>REG_LATEST_FORMAT</td>
<td>Save in the latest format. The latest format is supported starting with Windows XP. After the key is saved in this format, it cannot be loaded on an earlier version of Windows.</td>
</tr>
<tr>
<td>REG_NO_COMPRESSION</td>
<td>Save with no compression, for faster save operations. The registry key object must represent the root of a hive.</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>CallContext</b>

<dd>
<p>Optional driver-defined context information that the driver's <a href="kernel.registrycallback">RegistryCallback</a> routine can supply. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>ObjectContext</b>

<dd>
<p>A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved for future use. This member is defined starting with Windows Vista.</p>
</dd>
</dl>

## -remarks
<p>Note that when a key is saved, only the last component of the path can be changed.</p>

<p>For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista SP2.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="kernel.registrycallback">RegistryCallback</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_SAVE_KEY_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
