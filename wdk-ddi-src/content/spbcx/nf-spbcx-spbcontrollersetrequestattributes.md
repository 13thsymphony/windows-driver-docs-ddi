---
UID: NF:spbcx.SpbControllerSetRequestAttributes
title: SpbControllerSetRequestAttributes function
author: windows-driver-content
description: The SpbControllerSetRequestAttributes method sets object attributes that will be used for all SPBREQUEST objects that the SPB framework extension (SpbCx) delivers to the SPB controller driver.
old-location: spb\spbcontrollersetrequestattributes.htm
old-project: SPB
ms.assetid: 9BE790DB-DB7A-44A3-8A89-673CBFCF4D65
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: spbcx/SpbControllerSetRequestAttributes, SpbControllerSetRequestAttributes, SPB.spbcontrollersetrequestattributes, SpbControllerSetRequestAttributes method [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	spbcxstubs.lib
-	spbcxstubs.dll
apiname:
-	SpbControllerSetRequestAttributes
product: Windows
targetos: Windows
req.typenames: "*PSPB_REQUEST_TYPE, SPB_REQUEST_TYPE"
req.product: Windows 10 or later.
---


# SpbControllerSetRequestAttributes function
The <b>SpbControllerSetRequestAttributes</b> method  sets object attributes that will be used for all SPBREQUEST objects  that the SPB framework extension (SpbCx) delivers to the SPB controller driver.

## Syntax

````
VOID SpbControllerSetRequestAttributes(
  _In_ WDFDEVICE              FxDevice,
  _In_ PWDF_OBJECT_ATTRIBUTES RequestAttributes
);
````

## Parameters

`FxDevice`

A WDFDEVICE handle to the device object that represents the SPB controller.

`RequestAttributes`

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the SPB controller's SPBREQUEST objects.


## Return Value

None.

## Remarks

During device initialization, your SPB controller driver can call this method to set the default attributes for SPBREQUEST objects.  Thereafter, SpbCx assigns these attributes to any I/O requests that it delivers (or forwards) to target devices on the bus.

<i>RequestAttributes</i> points to an <b>WDF_OBJECT_ATTRIBUTES</b> structure. The caller must previously have called the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize this structure. After this call, but before the call to <b>SpbControllerSetRequestAttributes</b>, the caller can change the values of the following members of this structure:

<ul>
<li><b>EvtCleanupCallback</b></li>
<li><b>EvtDestroyCallback</b></li>
<li><b>ContextSizeOverride</b></li>
<li><b>ContextTypeInfo</b></li>
</ul>
<b>SpbControllerSetRequestAttributes</b> will use these values as default attributes for SPBREQUEST objects. However, the driver cannot change the default attribute values that are contained in the <b>ExecutionLevel</b>, <b>SynchronizationScope</b>, and <b>ParentObject</b> members.  These members must remain unchanged from the values that the <b>WDF_OBJECT_ATTRIBUTES_INIT</b> function initializes them to.

<b>WDF_OBJECT_ATTRIBUTES_INIT</b> initializes the <b>EvtCleanupCallback</b> and <b>EvtDestroyCallback</b> members to <b>NULL</b>. If you change these default values to register an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback function, this function is called each time an I/O request arrives in the SPB controller queue, which is managed by SpbCx. Such an I/O request causes the <i>EvtCleanupCallback</i> or <i>EvtDestroyCallback</i> function to be called even if SpbCx never presents the request to the SPB controller driver (because the request is canceled after it arrives in the queue but before it is passed to the driver).

The SPB controller driver must call <b>SpbControllerSetRequestAttributes</b> before it <i>commits</i> the device object—that is, before it returns from the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback or adds the PDO to the controller's child list. The child list represents the devices that are attached to the bus. For more information, see <a href="https://msdn.microsoft.com/5731db82-2bc8-4a8d-98f1-3977845f572c">Enumerating the Devices on a Bus</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Universal |
| **Header** | spbcx.h |
| **Library** | Spbcxstubs.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbControllerSetRequestAttributes method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>