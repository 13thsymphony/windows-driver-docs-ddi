---
UID: NS:fltkernel._FLT_TAG_DATA_BUFFER
title: "_FLT_TAG_DATA_BUFFER"
author: windows-driver-content
description: The FLT_TAG_DATA_BUFFER structure contains information about a reparse point tag.
old-location: ifsk\flt_tag_data_buffer.htm
old-project: ifsk
ms.assetid: a101e0c8-7121-42b6-aa0e-299f37af8e47
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FLT_TAG_DATA_BUFFER structure [Installable File System Drivers], ifsk.flt_tag_data_buffer, FltSystemStructures_47092b0b-5a4b-40eb-8b5f-f0a182d5e509.xml, FLT_TAG_DATA_BUFFER, *PFLT_TAG_DATA_BUFFER, PFLT_TAG_DATA_BUFFER, fltkernel/FLT_TAG_DATA_BUFFER, fltkernel/PFLT_TAG_DATA_BUFFER, _FLT_TAG_DATA_BUFFER, PFLT_TAG_DATA_BUFFER structure pointer [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltkernel.h
apiname:
-	FLT_TAG_DATA_BUFFER
product: Windows
targetos: Windows
req.typenames: FLT_TAG_DATA_BUFFER, *PFLT_TAG_DATA_BUFFER
---

# _FLT_TAG_DATA_BUFFER structure
The FLT_TAG_DATA_BUFFER structure contains information about a reparse point tag.

## Syntax
````
typedef struct _FLT_TAG_DATA_BUFFER {
  ULONG  FileTag;
  USHORT TagDataLength;
  USHORT UnparsedNameLength;
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
    struct {
      GUID  TagGuid;
      UCHAR DataBuffer[1];
    } GenericGUIDReparseBuffer;
  };
} FLT_TAG_DATA_BUFFER, *PFLT_TAG_DATA_BUFFER;
````

## Members


`FileTag`

Reparse point tag.

`TagDataLength`

Size, in bytes, of the reparse data pointed to by the <b>DataBuffer</b> member.

`UnparsedNameLength`

Length, in bytes, of the unparsed portion of the file name pointed to by the <b>FileName</b> member of the associated file object.  For more information about the <b>FileName</b> member, see <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>.

## Remarks
A minifilter can use the FLT_TAG_DATA_BUFFER structure to store information about a reparse point tag. 

A pointer to an FLT_TAG_DATA_BUFFER structure that contains reparse point tag data for an operation is stored in the <b>TagData</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> structure for the operation. 

The FLT_TAG_DATA_BUFFER_HEADER_SIZE macro returns the size of the fixed portion of the FLT_TAG_DATA_BUFFER structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | fltkernel.h (include FltKernel.h) |

## See Also

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>



<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>



<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_TAG_DATA_BUFFER structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>