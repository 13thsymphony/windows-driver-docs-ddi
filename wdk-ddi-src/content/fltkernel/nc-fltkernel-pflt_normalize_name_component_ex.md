---
UID: NC:fltkernel.PFLT_NORMALIZE_NAME_COMPONENT_EX
title: PFLT_NORMALIZE_NAME_COMPONENT_EX
author: windows-driver-content
description: A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's NormalizeNameComponentExCallback callback routine.
old-location: ifsk\pflt_normalize_name_component_ex.htm
old-project: ifsk
ms.assetid: 7c2bc90a-c724-4787-b604-f7257a83aae7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IXpsPartIterator, IXpsPartIterator::Reset, Reset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NormalizeNameComponentExCallback
req.alt-loc: fltkernel.h
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
req.typenames: EXpsFontRestriction
---

# PFLT_NORMALIZE_NAME_COMPONENT_EX callback



## -description
A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's <i>NormalizeNameComponentExCallback</i> callback routine.



## -prototype

````
PFLT_NORMALIZE_NAME_COMPONENT_EX NormalizeNameComponentExCallback;

NTSTATUS NormalizeNameComponentExCallback(
  _In_    PFLT_INSTANCE            Instance,
  _In_    PFILE_OBJECT             FileObject,
  _In_    PCUNICODE_STRING         ParentDirectory,
  _In_    USHORT                   VolumeNameLength,
  _In_    PCUNICODE_STRING         Component,
  _Out_   PFILE_NAMES_INFORMATION  ExpandComponentName,
  _In_    ULONG                    ExpandComponentNameLength,
  _In_    FLT_NORMALIZE_NAME_FLAGS Flags,
  _Inout_ PVOID                    *NormalizationContext
)
{ ... }
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the minifilter driver instance that this callback routine is registered for.


### -param FileObject [in]

Pointer to the file object for the file whose name is being requested or the file that is the target of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a> operation if the FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME flag is set.  See the <i>Flags</i> parameter below for more information.


### -param ParentDirectory [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the parent directory for this name component. 


### -param VolumeNameLength [in]

Length, in bytes, of the parent directory name that is stored in the structure that the <i>ParentDirectory</i> parameter points to. 


### -param Component [in]

Pointer to a UNICODE_STRING structure that contains the name component to be expanded. 


### -param ExpandComponentName [out]

Pointer to a <a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a> structure that receives the expanded (normalized) file name information for the name component. 


### -param ExpandComponentNameLength [in]

Length, in bytes, of the buffer that the <i>ExpandComponentName</i> parameter points to. 


### -param Flags [in]

Name normalization flags.  FLTFL_NORMALIZE_NAME_CASE_SENSITIVE specifies that the name to be normalized is case-sensitive.  FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME specifies that the callback routine has been called to service an <a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a> routine call.  If the FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME flag is set, <i>FileObject</i> represents the file/directory that is the target of the IRP_MJ_SET_INFORMATION operation. If the FLTFL_NORMALIZE_NAME_DESTINATION_FILE_NAME flag is not set, <i>FileObject</i> represents the file/directory whose name is being requested.


### -param NormalizationContext [in, out]

Pointer to minifilter driver-provided context information to be passed in any subsequent calls to this callback routine that are made to normalize the remaining components in the same file name path. 


## -returns
This callback routine returns STATUS_SUCCESS or an appropriate NTSTATUS value. If the name component that the <i>Component</i> parameter specifies does not exist in the parent directory that the <i>ParentDirectory</i> parameter specifies, this callback routine should return STATUS_NO_SUCH_FILE. If this callback routine issues an IRP_MN_QUERY_DIRECTORY (FileNamesInformation) request to the parent directory, the file system returns the correct status code. In this situation, this callback can simply return the status code that the file system returns.


## -remarks
A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's <i>NormalizeNameComponentExCallback</i> callback routine.  

The principal difference between the <i>NormalizeNameComponentExCallback</i> callback routine and the <i>NormalizeNameComponentCallback </i>callback routine (of type <a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a>) is that the <i>NormalizeNameComponentExCallback</i> callback routine supports the additional <i>FileObject</i> parameter.  The file object (<i>FileObject</i>) can be used by the minifilter driver to retrieve the <a href="..\ntddk\ns-ntddk-_txn_parameter_block.md">TXN_PARAMETER_BLOCK</a> structure for the operation that the file/directory is participating in by calling the <a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a> routine. The TXN_PARAMETER_BLOCK structure can be used by the minifilter driver to issue its own create requests in the context of the transaction that this file object is participating in. 

To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX in the <b>NormalizeNameComponentExCallback</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 

The filter manager calls this callback routine to query the minifilter driver for the normalized names for components in the file name path whose names the minifilter driver has modified. If the file name path contains more than one such component, the filter manager can call this callback routine multiple times in the process of normalizing all the components in the path. The minifilter driver can use the <i>NormalizationContext</i> parameter to pass context information to subsequent calls to this callback routine. 

If the minifilter driver uses the <i>NormalizationContext</i> parameter, it should also register a normalization context cleanup callback routine. For more information, see the reference entry for <a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>. 


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
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs-_file_names_information.md">FILE_NAMES_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iogettransactionparameterblock.md">IoGetTransactionParameterBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_generate_file_name.md">PFLT_GENERATE_FILE_NAME</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md">PFLT_NORMALIZE_CONTEXT_CLEANUP</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md">PFLT_NORMALIZE_NAME_COMPONENT</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_txn_parameter_block.md">TXN_PARAMETER_BLOCK</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_NORMALIZE_NAME_COMPONENT_EX routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

