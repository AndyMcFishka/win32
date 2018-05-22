---
Description: 'An association between an instance of the Msvm\_EthernetSwitchPort class and an instance of the Msvm\_EthernetPortData class that represents data gathered about the port by a switch extension.'
ms.assetid: '08677914-af09-47b7-9d4d-406696e1f504'
title: 'Msvm\_EthernetPortInfo class'
---

# Msvm\_EthernetPortInfo class

An association between an instance of the [**Msvm\_EthernetSwitchPort**](msvm-ethernetswitchport.md) class and an instance of the [**Msvm\_EthernetPortData**](msvm-ethernetportdata.md) class that represents data gathered about the port by a switch extension.

The following syntax is simplified Managed Object Format (MOF) code, and it includes all of the inherited properties.

## Syntax

``` syntax
[Association, Aggregation, Dynamic, Provider("VmmsWmiInstanceAndMethodProvider"), AMENDMENT]
class Msvm_EthernetPortInfo : CIM_Dependency
{
  Msvm_EthernetSwitchPort REF Antecedent;
  Msvm_EthernetPortData�� REF Dependent;
};
```

## Members

The **Msvm\_EthernetPortInfo** class has these types of members:

-   [Properties](#properties)

### Properties

The **Msvm\_EthernetPortInfo** class has these properties.

<dl> <dt>

**Antecedent**
</dt> <dd> <dl> <dt>

Data type: **Msvm\_EthernetSwitchPort**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("CIM\_Dependency.Antecedent")
</dt> </dl>

An instance of the [**Msvm\_EthernetSwitchPort**](msvm-ethernetswitchport.md) class that represents the switch port.

</dd> <dt>

**Dependent**
</dt> <dd> <dl> <dt>

Data type: **Msvm\_EthernetPortData**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("CIM\_Dependency.Dependent")
</dt> </dl>

An instance of the [**Msvm\_EthernetPortData**](msvm-ethernetportdata.md) class that represents the port data.

</dd> </dl>

## Requirements



|                                     |                                                                                                         |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�8 \[desktop apps only\]<br/>                                                              |
| Minimum supported server<br/> | Windows Server�2012 \[desktop apps only\]<br/>                                                    |
| Namespace<br/>                | Root\\Virtualization\\V2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



�

�



