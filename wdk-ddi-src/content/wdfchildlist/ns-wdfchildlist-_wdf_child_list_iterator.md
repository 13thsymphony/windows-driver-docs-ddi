---
UID : NS:wdfchildlist._WDF_CHILD_LIST_ITERATOR
title : "_WDF_CHILD_LIST_ITERATOR"
author : windows-driver-content
description : The WDF_CHILD_LIST_ITERATOR structure identifies the type of child devices that the framework will retrieve when a driver calls WdfChildListRetrieveNextDevice.
old-location : wdf\wdf_child_list_iterator.htm
old-project : wdf
ms.assetid : 3baeaaab-cb2f-49a1-bd01-01bd1e3e5214
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : DFDeviceObjectChildListRef_5a77ee51-8e18-4e86-afd0-8add561dab4d.xml, *PWDF_CHILD_LIST_ITERATOR, WDF_CHILD_LIST_ITERATOR structure, wdfchildlist/WDF_CHILD_LIST_ITERATOR, _WDF_CHILD_LIST_ITERATOR, WDF_CHILD_LIST_ITERATOR, PWDF_CHILD_LIST_ITERATOR structure pointer, PWDF_CHILD_LIST_ITERATOR, kmdf.wdf_child_list_iterator, wdf.wdf_child_list_iterator, wdfchildlist/PWDF_CHILD_LIST_ITERATOR
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfchildlist.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_CHILD_LIST_ITERATOR, *PWDF_CHILD_LIST_ITERATOR
req.product : Windows 10 or later.
---

# _WDF_CHILD_LIST_ITERATOR structure
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_LIST_ITERATOR</b> structure identifies the type of child devices that the framework will retrieve when a driver calls <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>.

## Syntax
````
typedef struct _WDF_CHILD_LIST_ITERATOR {
  ULONG Size;
  ULONG Flags;
  PVOID Reserved[4];
} WDF_CHILD_LIST_ITERATOR, *PWDF_CHILD_LIST_ITERATOR;
````

## Members


`Flags`

One or more flags that are defined by the <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a> enumeration.

`Reserved`

Reserved for internal use only.

`Size`

The size, in bytes, of this structure.

## Remarks
The driver must initialize the <b>WDF_CHILD_LIST_ITERATOR</b> structure by calling <a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_iterator_init.md">WDF_CHILD_LIST_ITERATOR_INIT</a>.

The WDF_CHILD_LIST_ITERATOR structure is used as input to the <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>,<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> ,and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a> methods. The driver must set the <b>Flags</b> member before calling <b>WdfChildListBeginIteration</b>. After calling <b>WdfChildListBeginIteration</b>, the driver must not modify the structure's contents until after calling <b>WdfChildListEndIteration</b>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfchildlist.h (include Wdf.h) |

## See Also

<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_iterator_init.md">WDF_CHILD_LIST_ITERATOR_INIT</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>

<a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_LIST_ITERATOR structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>