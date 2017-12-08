# Wdfdpc.h header


This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfdpc.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_DPC_CONFIG_INIT function](nf-wdfdpc-wdf-dpc-config-init.md) | The WDF_DPC_CONFIG_INIT function initializes a driver's WDF_DPC_CONFIG structure. |
| [WdfDpcCancel function](nf-wdfdpc-wdfdpccancel.md) | The WdfDpcCancel method attempts to cancel the execution of a DPC object's scheduled EvtDpcFunc callback function. |
| [WdfDpcCreate function](nf-wdfdpc-wdfdpccreate.md) | The WdfDpcCreate method creates a framework DPC object and registers an EvtDpcFunc callback function. |
| [WdfDpcEnqueue function](nf-wdfdpc-wdfdpcenqueue.md) | The WdfDpcEnqueue method schedules the execution of a DPC object's EvtDpcFunc callback function. |
| [WdfDpcGetParentObject function](nf-wdfdpc-wdfdpcgetparentobject.md) | The WdfDpcGetParentObject method returns the parent object of a specified DPC object. |
| [WdfDpcWdmGetDpc function](nf-wdfdpc-wdfdpcwdmgetdpc.md) | The WdfDpcWdmGetDpc method returns a pointer to the KDPC structure that is associated with a specified framework DPC object. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [WDF_DPC_CONFIG structure](ns-wdfdpc--wdf-dpc-config.md) | The WDF_DPC_CONFIG structure contains configuration information for a DPC object. |
