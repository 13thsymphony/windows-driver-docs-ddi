---
UID : NF:wudfworkitem.WUDF_WORKITEM_CONFIG_INIT
title : WUDF_WORKITEM_CONFIG_INIT function
author : windows-driver-content
description : The WUDF_WORKITEM_CONFIG_INIT macro initializes a driver's WUDF_WORKITEM_CONFIG structure.
old-location : wdf\wudf_workitem_config_init.htm
old-project : wdf
ms.assetid : A75AE18F-802F-462B-BF96-5C03408F53CA
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WUDF_WORKITEM_CONFIG_INIT, wudfworkitem/WUDF_WORKITEM_CONFIG_INIT, wdf.wudf_workitem_config_init, WUDF_WORKITEM_CONFIG_INIT function, umdf.wudf_workitem_config_init
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wudfworkitem.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.11
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : UNICODE_STRING
req.product : Windows 10 or later.
---


# WUDF_WORKITEM_CONFIG_INIT function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The 
  <b>WUDF_WORKITEM_CONFIG_INIT</b> macro initializes a driver's <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure.

## Syntax

````
void WUDF_WORKITEM_CONFIG_INIT(
  _Out_ PWUDF_WORKITEM_CONFIG pConfig,
  _In_  PFN_WUDF_WORKITEM     OnWorkItemFunc
);
````

## Parameters

`pConfig`

A pointer to the caller-allocated <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure to initialize.

`OnWorkItemFunc`

The address of the driver's <a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a> event callback function.


## Return Value

This function does not return a value.

## Remarks

Drivers must call <b>WUDF_WORKITEM_CONFIG_INIT</b> before calling <a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>.

The <b>WUDF_WORKITEM_CONFIG_INIT</b> function stores the pointer that the <i>OnWorkItemFunc</i> parameter specifies and sets the <b>AutomaticSerialization</b> member of the <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure that is pointed to by the <i>pConfig</i> parameter to <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfworkitem.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a>

<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_WORKITEM_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>