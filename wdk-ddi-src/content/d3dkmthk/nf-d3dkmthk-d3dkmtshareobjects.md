---
UID : NF:d3dkmthk.D3DKMTShareObjects
title : D3DKMTShareObjects function
author : windows-driver-content
description : Shares resource objects that were created with the D3DKMTCreateAllocation, D3DKMTCreateKeyedMutex2, and D3DKMTCreateSynchronizationObject2 functions.
old-location : display\d3dkmtshareobjects.htm
old-project : display
ms.assetid : 853c4e73-b571-4b68-8690-bbef7a726c8e
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTShareObjects, d3dkmthk/D3DKMTShareObjects, display.d3dkmtshareobjects, D3DKMTShareObjects function [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Universal
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : GDI32.lib
req.dll : GDI32.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTShareObjects function
Shares resource objects that were created with  the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a>, <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a>, and  <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md">D3DKMTCreateSynchronizationObject2</a> functions.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTShareObjects(
  _In_        UINT               cObjects,
  _In_  const D3DKMT_HANDLE      *hObjects,
  _In_        POBJECT_ATTRIBUTES pObjectAttributes,
  _In_        DWORD              dwDesiredAccess,
  _Out_       HANDLE             *phSharedNtHandle
);
````

## Parameters

`cObjects`

The number of resource objects specified by the <i>hObjects</i> parameter.

The number of resource objects must be ≤<b>D3DKMT_MAX_OBJECTS_PER_HANDLE</b>.

`hObjects`

A pointer to an array of local kernel-mode handles that specify the resource objects to be shared.

For more information on using <i>hObjects</i>, see the Remarks section.

`pObjectAttributes`

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies attributes of the  resource objects.

`dwDesiredAccess`

Specifies read and write access for the resource.

`phSharedNtHandle`

A pointer to a shared NT handle  that specifies the resource objects.

This parameter must be <b>NULL</b> if the <b>NtSecuritySharing</b> flag value is not set. For more information, see the Remarks section.


## Return Value

None

## Remarks

Objects to be shared using  <b>D3DKMTShareObjects</b>  must first be created with the <b>NtSecuritySharing</b> flag value set. This flag value is available in the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocationflags.md">D3DKMT_CREATEALLOCATIONFLAGS</a>, <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>, and <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a> structures.

This function must specify handles through the <i>hObjects</i> parameter only to the following  combinations of input object array types:
<ul>
<li>an allocation</li>
<li>an allocation, a keyed mutex, and a synchronization object</li>
<li>a synchronization object</li>
</ul>The operating system will reject any other input handle combinations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createallocationflags.md">D3DKMT_CREATEALLOCATIONFLAGS</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateallocation.md">D3DKMTCreateAllocation</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatekeyedmutex2.md">D3DKMTCreateKeyedMutex2</a>

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_synchronizationobject_flags.md">D3DDDI_SYNCHRONIZATIONOBJECT_FLAGS</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2_flags.md">D3DKMT_CREATEKEYEDMUTEX2_FLAGS</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md">D3DKMTCreateSynchronizationObject2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTShareObjects function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>