---
UID: NF.ntddk.WheaFindNextErrorRecordSection
title: WheaFindNextErrorRecordSection function
author: windows-driver-content
description: The WheaFindNextErrorRecordSection function allows a caller to iteratively examine the WHEA error record sections within a WHEA error record. Each error record section is formatted as a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.
old-location: whea\wheafindnexterrorrecordsection.htm
old-project: whea
ms.assetid: 36a0ca45-2601-4b7f-9f2b-35e2a7047520
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: WheaFindNextErrorRecordSection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WheaFindNextErrorRecordSection
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# WheaFindNextErrorRecordSection function



## -description
The <b>WheaFindNextErrorRecordSection</b> function allows a caller to iteratively examine the WHEA error record sections within a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. Each error record section is formatted as a <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure.



## -syntax

````
NTSTATUS WheaFindNextErrorRecordSection(
  _In_      PWHEA_ERROR_RECORD                    Record,
  _Inout_   ULONG                                 *Context,
  _Out_     PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR *SectionDescriptor,
  _Out_opt_ PVOID                                 *SectionData
);
````


## -parameters

### -param Record [in]

A pointer to a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a> that is formatted as a <a href="whea.whea_error_record">WHEA_ERROR_RECORD</a> structure.


### -param Context [in, out]

A pointer to a ULONG variable that maintains the current state of the search. 

<div class="alert"><b>Note</b>  This variable must be initialized to zero before the first call to the <b>WheaFindNextErrorRecordSection </b>function<b>.</b></div>
<div> </div>

### -param SectionDescriptor [out]

The address of a <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> pointer. 

If the <b>WheaFindNextErrorRecordSection </b>function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the function sets the <i>SectionDescriptor </i>parameter to the address of that structure within the specified WHEA error record.


### -param SectionData [out, optional]

The address of a PVOID pointer.

If the <b>WheaFindNextErrorRecordSection</b> function locates the next <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure within the specified WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>, the function sets the <i>SectionData</i> parameter to the address of the hardware error data associated with that descriptor.

<div class="alert"><b>Note</b>  This parameter is optional and must be set to <b>NULL</b> if a pointer to the error record section data is not required.</div>
<div> </div>

## -returns
<b>WheaFindNextErrorRecordSection</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The next  <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was found. 
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The next <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure was not found.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Either the <i>Record</i>, <i>SectionType,</i> or <i>SectionDescriptor</i> parameters were set to <b>NULL</b>, or the <a href="whea.whea_error_record">WHEA_ERROR_RECORD</a> data referenced through the <i>Record </i>parameter is invalid.

 


## -remarks
If the <i>Context</i> parameter is set to 0, <b>WheaFindNextErrorRecordSection </b>returns a pointer to the first <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure within a WHEA <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. <b>WheaFindNextErrorRecordSection </b>will also update the <i>Context</i> parameter with state information related to the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR returned through the <i>SectionDescriptor</i> parameter.

On subsequent calls to <b>WheaFindNextErrorRecordSection</b>, the function returns the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure (if available) within the WHEA error record. If the function locates the next WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure, it will update the <i>Context</i> parameter. Otherwise, the function will return STATUS_NOT_FOUND.

Additionally, if <b>WheaFindNextErrorRecordSection</b> returns STATUS_SUCCESS and the caller set the <i>SectionData</i> parameter to the address of a PVOID pointer variable, the function updates the parameter with the address of the hardware error data associated with the specified <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure. 

The format of the hardware error data depends upon the <b>SectionType </b>member of the <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure that is referenced through the <i>SectionDescriptor </i>parameter. For example, if the <b>SectionType </b>member has the value PROCESSOR_GENERIC_ERROR_SECTION_GUID, the hardware error data is formatted as a <a href="whea.whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows 7 and later versions of Windows.


</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">Error record</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="whea.whea_error_record">WHEA_ERROR_RECORD</a>
</dt>
<dt>
<a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WheaFindNextErrorRecordSection function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

