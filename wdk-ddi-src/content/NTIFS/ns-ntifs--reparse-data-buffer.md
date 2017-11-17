---
UID: NS.ntifs._REPARSE_DATA_BUFFER
title: REPARSE_DATA_BUFFER
author: windows-driver-content
description: The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point.
old-location: ifsk\reparse_data_buffer.htm
ms.assetid: e906a874-51f1-4623-8f0b-afdfd8169ab2
ms.author: windowsdriverdev
ms.date: 10/26/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: ifsk
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REPARSE_DATA_BUFFER
req.alt-loc: ntifs.h
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
ms.keywords: REPARSE_DATA_BUFFER, REPARSE_DATA_BUFFER, *PREPARSE_DATA_BUFFER
req.iface: 
---

# REPARSE_DATA_BUFFER structure



## -description
<p>The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point. (Third-party reparse point owners must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552014">REPARSE_GUID_DATA_BUFFER</a> structure instead.) </p>


## -syntax

````
typedef struct _REPARSE_DATA_BUFFER {
  ULONG  ReparseTag;
  USHORT ReparseDataLength;
  USHORT Reserved;
  union {
    struct {
      USHORT SubstituteNameOffset;
      USHORT SubstituteNameLength;
      USHORT PrintNameOffset;
      USHORT PrintNameLength;
      ULONG  Flags;
      WCHAR  PathBuffer[1];
    } SymbolicLinkReparseBuffer;
    struct {
      USHORT SubstituteNameOffset;
      USHORT SubstituteNameLength;
      USHORT PrintNameOffset;
      USHORT PrintNameLength;
      WCHAR  PathBuffer[1];
    } MountPointReparseBuffer;
    struct {
      UCHAR DataBuffer[1];
    } GenericReparseBuffer;
  };
} REPARSE_DATA_BUFFER, *PREPARSE_DATA_BUFFER;
````


## -struct-fields
<dl>

### -field <b>ReparseTag</b>

<dd>
<p>Reparse point tag. Must be a Microsoft reparse point tag. (See the following <b>Remarks</b> section.) </p>
</dd>

### -field <b>ReparseDataLength</b>

<dd>
<p>Size, in bytes, of the reparse data in the <b>DataBuffer</b> member. </p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Length, in bytes, of the unparsed portion of the file name pointed to by the <b>FileName</b> member of the associated file object. For more information about the <b>FileName</b> member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>. This member is only valid for create operations when the I/O fails with STATUS_REPARSE. For all other purposes, such as setting or querying a reparse point for the reparse data, this member is treated as reserved.</p>
</dd>

### -field ( <i>unnamed union</i> )

<dd>
<p> </p>
<dl>

### -field <b>SymbolicLinkReparseBuffer</b>

<dd>
<dl>

### -field <b>SubstituteNameOffset</b>

<dd>
<p>Offset, in bytes, of the substitute name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. </p>
</dd>

### -field <b>SubstituteNameLength</b>

<dd>
<p>Length, in bytes, of the substitute name string. If this string is NULL-terminated, <b>SubstituteNameLength</b> does not include space for the UNICODE_NULL character. </p>
</dd>

### -field <b>PrintNameOffset</b>

<dd>
<p>Offset, in bytes, of the print name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. </p>
</dd>

### -field <b>PrintNameLength</b>

<dd>
<p>Length, in bytes, of the print name string. If this string is NULL-terminated, <b>PrintNameLength</b> does not include space for the UNICODE_NULL character. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Used to indicate if the given symbolic link is an absolute or relative symbolic link.  If <b>Flags</b> contains SYMLINK_FLAG_RELATIVE, the symbolic link contained in the <b>PathBuffer</b> array (at offset <b>SubstitueNameOffset</b>) is processed as a relative symbolic link; otherwise, it is processed as an absolute symbolic link.</p>
</dd>

### -field <b>PathBuffer</b>

<dd>
<p>First character of the path string. This is followed in memory by the remainder of the string. The path string contains the substitute name string and print name string. The substitute name and print name strings can appear in any order in the <b>PathBuffer</b>. (To locate the substitute name and print name strings in the <b>PathBuffer</b>, use the <b>SubstituteNameOffset</b>, <b>SubstituteNameLength</b>, <b>PrintNameOffset</b>, and <b>PrintNameLength</b> members.) </p>
</dd>
</dl>
</dd>

### -field <b>MountPointReparseBuffer</b>

<dd>
<dl>

### -field <b>SubstituteNameOffset</b>

<dd>
<p>Offset, in bytes, of the substitute name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. </p>
</dd>

### -field <b>SubstituteNameLength</b>

<dd>
<p>Length, in bytes, of the substitute name string. If this string is NULL-terminated, <b>SubstituteNameLength</b> does not include space for the UNICODE_NULL character. </p>
</dd>

### -field <b>PrintNameOffset</b>

<dd>
<p>Offset, in bytes, of the print name string in the <b>PathBuffer</b> array. Note that this offset must be divided by <b>sizeof</b>(WCHAR) to get the array index. </p>
</dd>

### -field <b>PrintNameLength</b>

<dd>
<p>Length, in bytes, of the print name string. If this string is NULL-terminated, <b>PrintNameLength</b> does not include space for the UNICODE_NULL character. </p>
</dd>

### -field <b>PathBuffer</b>

<dd>
<p>First character of the path string. This is followed in memory by the remainder of the string. The path string contains the substitute name string and print name string. The substitute name and print name strings can appear in any order in the <b>PathBuffer</b>. (To locate the substitute name and print name strings in the <b>PathBuffer</b>, use the <b>SubstituteNameOffset</b>, <b>SubstituteNameLength</b>, <b>PrintNameOffset</b>, and <b>PrintNameLength</b> members.) </p>
</dd>
</dl>
</dd>

### -field <b>GenericReparseBuffer</b>

<dd>
<dl>

### -field <b>DataBuffer</b>

<dd>
<p>Microsoft-defined data for the reparse point. </p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The REPARSE_DATA_BUFFER structure is used by Microsoft file systems, filters, and minifilter drivers, as well as the I/O manager, to store data for a reparse point. </p>

<p>This structure can only be used for Microsoft reparse points. Third-party reparse point owners must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552014">REPARSE_GUID_DATA_BUFFER</a> structure instead. </p>

<p>Microsoft reparse points can use the REPARSE_DATA_BUFFER structure or the REPARSE_GUID_DATA_BUFFER structure. </p>

<p>For more information about reparse point tags, see the Microsoft Windows SDK documentation. </p>

<p>For more information about absolute and relative symbolic links, see Creating Symbolic Links in the Microsoft Windows SDK documentation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540354">FILE_REPARSE_POINT_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549452">IsReparseTagMicrosoft</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549462">IsReparseTagNameSurrogate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552014">REPARSE_GUID_DATA_BUFFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20REPARSE_DATA_BUFFER structure%20 RELEASE:%20(10/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
