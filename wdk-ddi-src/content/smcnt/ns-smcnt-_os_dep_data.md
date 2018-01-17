---
UID: NS:smcnt._OS_DEP_DATA
title: _OS_DEP_DATA
author: windows-driver-content
description: The OS_DEP_DATA structure defines the data that is stored in the OsData member of the SMARTCARD_EXTENSION structure, which holds smart card information that is specific to the operating system.
old-location: smartcrd\os_dep_data__wdm_.htm
old-project: smartcrd
ms.assetid: 76f6f0d1-cb2f-4cda-aeb0-7421e18e3c27
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _OS_DEP_DATA, *POS_DEP_DATA, OS_DEP_DATA
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
req.alt-api: OS_DEP_DATA
req.alt-loc: smcnt.h
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
req.typenames: *POS_DEP_DATA, OS_DEP_DATA
req.product: Windows 10 or later.
---

# _OS_DEP_DATA structure



## -description
The OS_DEP_DATA structure defines the data that is stored in the <b>OsData</b> member of the <a href="..\smclib\ns-smclib-_smartcard_extension.md">SMARTCARD_EXTENSION</a> structure, which holds smart card information that is specific to the operating system. 



## -syntax

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


## -struct-fields

### -field DeviceObject

A pointer to the smart card reader device object. (Must be set by the driver.)


### -field CurrentIrp

A pointer to the current IRP to process. Access to this field must be sequentialized by using the spin lock pointed to by the <b>OsData-&gt;SpinLock</b> member of <a href="..\smclib\ns-smclib-_smartcard_extension.md">SMARTCARD_EXTENSION</a>. 


### -field NotificationIrp

A pointer to an IRP that the smart card reader driver uses to notify applications when a smart card has been inserted or removedl. Access to this field must be sequentialized by using the spin lock that is pointed to by the <b>OsData-&gt;SpinLock</b> member of SMARTCARD_EXTENSION.  


### -field Mutex

Contains a mutex that applications use to synchronize access to the reader driver. 


### -field SpinLock

Contains a mutex that drivers use to synchronize access to protected members of the OS_DEP_DATA structure. For more information, see <a href="..\smclib\ns-smclib-_scard_card_capabilities.md">SCARD_CARD_CAPABILITIES</a>.


### -field RemoveLock

A structure with the following members:


### -field Removed

If this Boolean value is non-zero, it indicates that the spin lock was removed.


### -field RefCount

If this long integer is non-zero, it indicates the number of references to the spin lock that are currently active. 


### -field RemoveEvent

A pointer to an event that synchronizes spin lock removal.


### -field TagList

A pointer to a linked list of structures, each of which contains a tag string that identifies a remove spin lock. 

</dd>
</dl>

### -field DebugDeviceObject

Unused.


## -remarks
To allocate this structure, drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548944">SmartcardInitialize (WDM)</a>. After this call, drivers should copy the pointer of the smart card device object to <b>DeviceObject</b>. Otherwise, the smart card driver library will not work. Do not use this structure to store driver-dependent information. However, when the smart card driver library calls one of your driver's callback functions, it sets <b>CurrentIrp</b> to the requesting IRP, unless the request is a smart card tracking request. For smart card tracking requests, the driver library sets <b>NotificationIrp</b> to the requesting IRP. For more information about smart card tracking, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548920">RDF_CARD_TRACKING</a>.</p>