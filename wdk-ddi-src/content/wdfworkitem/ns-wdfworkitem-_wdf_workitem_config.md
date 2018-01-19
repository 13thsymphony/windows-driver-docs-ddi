---
UID : NS:wdfworkitem._WDF_WORKITEM_CONFIG
title : _WDF_WORKITEM_CONFIG
author : windows-driver-content
description : The WDF_WORKITEM_CONFIG structure contains information that is associated with a work item.
old-location : wdf\wdf_workitem_config.htm
old-project : wdf
ms.assetid : b6186c05-ccb9-432c-bd83-9a3fb3af7f0b
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDF_WORKITEM_CONFIG, *PWDF_WORKITEM_CONFIG, WDF_WORKITEM_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdfworkitem.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : WDF_WORKITEM_CONFIG
req.alt-loc : wdfworkitem.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PWDF_WORKITEM_CONFIG, WDF_WORKITEM_CONFIG"
req.product : Windows 10 or later.
---

# _WDF_WORKITEM_CONFIG structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_WORKITEM_CONFIG</b> structure contains information that is associated with a work item.

## Syntax
````
typedef struct _WDF_WORKITEM_CONFIG {
  ULONG            Size;
  PFN_WDF_WORKITEM EvtWorkItemFunc;
  BOOLEAN          AutomaticSerialization;
} WDF_WORKITEM_CONFIG, *PWDF_WORKITEM_CONFIG;
````

## Members

        
            `AutomaticSerialization`

            A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function with callback functions from other objects that are underneath the work-item object's parent object. For more information, see the following Remarks section. If <b>FALSE</b>, the framework does not synchronize execution of the <i>EvtWorkItem</i> callback function.
        
            `EvtWorkItemFunc`

            The address of an <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> event callback function.
        
            `Size`

            The size, in bytes, of this <b>WDF_WORKITEM_CONFIG</b> structure.

    ## Remarks
        Your driver must initialize the <b>WDF_WORKITEM_CONFIG</b> structure by calling <a href="..\wdfworkitem\nf-wdfworkitem-wdf_workitem_config_init.md">WDF_WORKITEM_CONFIG_INIT</a>. Your driver can then pass the structure to the <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a> method as an input parameter.

Setting the <b>AutomaticSerialization</b> member of <b>WDF_WORKITEM_CONFIG</b> to <b>TRUE</b> has no effect if the parent object's <a href="..\wdfobject\ne-wdfobject-_wdf_synchronization_scope.md">synchronization scope</a> is set to <b>WdfSynchronizationScopeNone</b>.

If <b>AutomaticSerialization</b> is <b>TRUE</b>, the parent object's execution level must be <b>WdfExecutionLevelPassive</b>.

For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfworkitem.h (include Wdf.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a>
</dt>
<dt>
<a href="..\wdfworkitem\nf-wdfworkitem-wdf_workitem_config_init.md">WDF_WORKITEM_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WORKITEM_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>