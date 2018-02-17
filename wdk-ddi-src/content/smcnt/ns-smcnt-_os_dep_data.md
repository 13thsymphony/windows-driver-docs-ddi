---
UID: NS:smcnt._OS_DEP_DATA
title: "_OS_DEP_DATA"
author: windows-driver-content
description: The OS_DEP_DATA structure defines the data that is stored in the OsData member of the SMARTCARD_EXTENSION structure, which holds smart card information that is specific to the operating system.
old-location: smartcrd\os_dep_data__wdm_.htm
old-project: smartcrd
ms.assetid: 76f6f0d1-cb2f-4cda-aeb0-7421e18e3c27
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: smcnt/OS_DEP_DATA, OS_DEP_DATA structure [Smart Card Reader Devices], smcnt/POS_DEP_DATA, *POS_DEP_DATA, OS_DEP_DATA (WDM) structure [Smart Card Reader Devices], POS_DEP_DATA structure pointer [Smart Card Reader Devices], _OS_DEP_DATA, OS_DEP_DATA, scstruct_f7288ef8-a011-44c0-ab86-db7cc6d1a985.xml, smartcrd.os_dep_data__wdm_, OS_DEP_DATA (WDM), POS_DEP_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smcnt.h
req.include-header: Smcnt.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	smcnt.h
apiname:
-	OS_DEP_DATA
product: Windows
targetos: Windows
req.typenames: OS_DEP_DATA, *POS_DEP_DATA
req.product: Windows 10 or later.
---

# _OS_DEP_DATA structure
The OS_DEP_DATA structure defines the data that is stored in the <b>OsData</b> member of the <a href="..\smclib\ns-smclib-_smartcard_extension.md">SMARTCARD_EXTENSION</a> structure, which holds smart card information that is specific to the operating system.

## Syntax
````
typedef struct _OS_DEP_DATA {
  PDEVICE_OBJECT DeviceObject;
  PIRP           CurrentIrp;
  PIRP           NotificationIrp;
  KMUTANT        Mutex;
  KSPIN_LOCK     SpinLock;
  struct {
    BOOLEAN    Removed;
    LONG       RefCount;
    KEVENT     RemoveEvent;
    LIST_ENTRY TagList;
  } RemoveLock;
#ifdef DEBUG_INTERFACE
  PDEVICE_OBJECT DebugDeviceObject;
#endif 
} OS_DEP_DATA, *POS_DEP_DATA;
````

## Members


`CurrentIrp`

A pointer to the current IRP to process. Access to this field must be sequentialized by using the spin lock pointed to by the <b>OsData-&gt;SpinLock</b> member of <a href="..\smclib\ns-smclib-_smartcard_extension.md">SMARTCARD_EXTENSION</a>.

`DebugDeviceObject`

Unused.

`DeviceObject`

A pointer to the smart card reader device object. (Must be set by the driver.)

`Mutex`

Contains a mutex that applications use to synchronize access to the reader driver.

`NotificationIrp`

A pointer to an IRP that the smart card reader driver uses to notify applications when a smart card has been inserted or removedl. Access to this field must be sequentialized by using the spin lock that is pointed to by the <b>OsData-&gt;SpinLock</b> member of SMARTCARD_EXTENSION.

`RemoveLock`

A structure with the following members:

`SpinLock`

Contains a mutex that drivers use to synchronize access to protected members of the OS_DEP_DATA structure. For more information, see <a href="..\smclib\ns-smclib-_scard_card_capabilities.md">SCARD_CARD_CAPABILITIES</a>.

## Remarks
To allocate this structure, drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548944">SmartcardInitialize (WDM)</a>. After this call, drivers should copy the pointer of the smart card device object to <b>DeviceObject</b>. Otherwise, the smart card driver library will not work. Do not use this structure to store driver-dependent information. However, when the smart card driver library calls one of your driver's callback functions, it sets <b>CurrentIrp</b> to the requesting IRP, unless the request is a smart card tracking request. For smart card tracking requests, the driver library sets <b>NotificationIrp</b> to the requesting IRP. For more information about smart card tracking, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548920">RDF_CARD_TRACKING</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | smcnt.h (include Smcnt.h) |