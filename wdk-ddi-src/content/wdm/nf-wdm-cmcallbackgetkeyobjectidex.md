---
UID: NF:wdm.CmCallbackGetKeyObjectIDEx
title: CmCallbackGetKeyObjectIDEx function
author: windows-driver-content
description: The CmCallbackGetKeyObjectIDEx routine retrieves the unique identifier and object name that are associated with a specified registry key object.
old-location: kernel\cmcallbackgetkeyobjectidex.htm
old-project: kernel
ms.assetid: E55CDAF9-2711-4DC6-8BED-EDB0D78D9158
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/CmCallbackGetKeyObjectIDEx, CmCallbackGetKeyObjectIDEx, kernel.cmcallbackgetkeyobjectidex, CmCallbackGetKeyObjectIDEx routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CmCallbackGetKeyObjectIDEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# CmCallbackGetKeyObjectIDEx function
The <b>CmCallbackGetKeyObjectIDEx</b> routine retrieves the unique identifier and object name that are associated with a specified registry key object.
<div class="alert"><b>Note</b>  This routine is available starting with Windows 8. In earlier versions of Windows, use the <a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectid.md">CmCallbackGetKeyObjectID</a> routine instead. For more information, see Remarks.</div><div> </div>

## Syntax

````
NTSTATUS CmCallbackGetKeyObjectIDEx(
  _In_      PLARGE_INTEGER   Cookie,
  _In_      PVOID            Object,
  _Out_opt_ PULONG_PTR       ObjectID,
  _Out_opt_ PCUNICODE_STRING *ObjectName,
  _In_      ULONG            Flags
);
````

## Parameters

`Cookie`

A cookie value that represents the caller's registration to receive registry filter callbacks. The driver previously obtained this cookie value from the <a href="..\wdm\nf-wdm-cmregistercallback.md">CmRegisterCallback</a> or <a href="..\wdm\nf-wdm-cmregistercallbackex.md">CmRegisterCallbackEx</a> routine.

`Object`

A pointer to the registry key object. This parameter is the pointer value that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> callback routine received in the <b>Object</b> member of one of the <b>REG_<i>XXX</i>_KEY_INFORMATION</b> structures.

<div class="alert"><b>Warning</b>  In certain circumstances registry callback notification structures may contain invalid non-NULL object pointers. Registry filtering drivers must not pass such pointers to this routine. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=613134">Invalid Key Object Pointers in Registry Notifications</a>.</div>
<div> </div>

`ObjectID`

A pointer to a location that receives a pointer to the key identifier for the registry key that <i>Object</i> represents. This identifier is unique across all keys in the registry. This parameter is optional and can be <b>NULL</b>. For more information, see Remarks.

`ObjectName`

A pointer to a location that receives a pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure. This structure contains the object name of the registry key object that <i>Object</i> specifies. The object name is actually the full path name of the registry key that the object represents. The caller is responsible for freeing this structure by calling the <a href="..\wdm\nf-wdm-cmcallbackreleasekeyobjectidex.md">CmCallbackReleaseKeyObjectIDEx</a> routine. This parameter is optional and can be <b>NULL</b>. For more information, see Remarks.

`Flags`

Reserved. Set to zero.


## Return Value

<b>CmCallbackGetKeyObjectIDEx</b> returns STATUS_SUCCESS if the operation succeeds. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Cookie</i>, <i>Object</i>, or <i>Flags</i> parameter is invalid.

</td>
</tr>
</table>

## Remarks

Drivers can use <b>CmCallbackGetKeyObjectIDEx</b> to obtain the registry key identifier, the object name, or both, by supplying non-<b>NULL</b> values for the <i>ObjectID</i> or <i>ObjectName</i> parameters.

The caller can obtain the key identifier through the <i>ObjectID</i> parameter. If two registry key objects represent the same registry key, the key identifiers obtained from <b>CmCallbackGetKeyObjectIDEx</b> for the two objects are identical. If the name of the  registry key changes, the key identifier obtained from <b>CmCallbackGetKeyObjectIDEx</b> does not change. The caller can use the key identifier to reliably track accesses that are made to a particular registry key through multiple key objects, and even across changes to the registry key name.

The caller can obtain the object name through the <i>ObjectName</i> parameter. The storage for the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the object name remains valid until the caller calls <a href="..\wdm\nf-wdm-cmcallbackreleasekeyobjectidex.md">CmCallbackReleaseKeyObjectIDEx</a> to free the structure.

<b>CmCallbackGetKeyObjectIDEx</b> is an improved version of the <a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectid.md">CmCallbackGetKeyObjectID</a> routine, which is available starting with Windows Vista. Drivers that run in versions of Windows earlier than Windows 8 should call <b>CmCallbackGetKeyObjectID</b> instead of <b>CmCallbackGetKeyObjectIDEx</b>. Drivers that run only in Windows 8 and later versions of Windows should call <b>CmCallbackGetKeyObjectIDEx</b> instead of <b>CmCallbackGetKeyObjectID</b>.

<b>CmCallbackGetKeyObjectIDEx</b> has two important features that are not available from <b>CmCallbackGetKeyObjectID</b>.

First, <b>CmCallbackGetKeyObjectIDEx</b> enables a registry filter driver to explicitly control the lifetime of the <i>ObjectName</i> structure. The driver can call <b>CmCallbackReleaseKeyObjectIDEx</b> at any time to free this structure. In contrast, the driver cannot explicitly free the <i>ObjectName</i> structure received from <b>CmCallbackGetKeyObjectID</b>. This structure is automatically released when all handles to the key are closed.

Second, if a registry filter driver calls <b>CmCallbackReleaseKeyObjectID</b> to get an <i>ObjectName</i> structure pointer, and, after this call, the name of the registry key changes, subsequent calls to <b>CmCallbackGetKeyObjectID</b> get a pointer to a stale copy of the <i>ObjectName</i> structure, which contains the old key name. The stale copy of this structure persists until all handles to the key are closed. In contrast, the <i>ObjectName</i> structure obtained from <b>CmCallbackGetKeyObjectIDEx</b> always contains the most up-to-date key name.

For more information about registry filter drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>



<a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectid.md">CmCallbackGetKeyObjectID</a>



<a href="..\wdm\nf-wdm-cmcallbackreleasekeyobjectidex.md">CmCallbackReleaseKeyObjectIDEx</a>



<a href="..\wdm\nf-wdm-cmregistercallback.md">CmRegisterCallback</a>



<a href="..\wdm\nf-wdm-cmcallbackgetkeyobjectid.md">CmCallbackGetKeyObjectID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CmCallbackGetKeyObjectIDEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>