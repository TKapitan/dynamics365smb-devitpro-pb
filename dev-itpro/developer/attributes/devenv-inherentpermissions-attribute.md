---
title: "InherentPermissions Attribute"
description: "Specifies the permissions assigned to the scope of the method."
ms.author: solsen
ms.date: 10/18/2022
ms.topic: reference
author: SusanneWindfeldPedersen
ms.reviewer: solsen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)

# InherentPermissions Attribute
> **Version**: _Available or changed with runtime version 9.0._

Specifies the permissions assigned to the scope of the method. 


## Applies To

- Method
- Event


## Syntax

```AL
[InherentPermissions(PermissionObjectType: PermissionObjectType, ObjectId: Integer, Permissions: Text [, InherentPermissionsScope: InherentPermissionsScope])]
```

### Arguments
*PermissionObjectType*  
&emsp;Type: [PermissionObjectType](../methods-auto/permissionobjecttype/permissionobjecttype-option.md)  
Specifies the type of object that the attribute assigns permissions to.  

*ObjectId*  
&emsp;Type: [Integer](../methods-auto/integer/integer-data-type.md)  
Specifies the ID of the object that permissions are assigned to. You can specify the object by its ID (integer) or by its name using the syntax `<ObjectType>::<ObjectName>`, such as `Codeunit::MyCodeunit`. It is recommended to specify the object by name for readability.  

*Permissions*  
&emsp;Type: [Text](../methods-auto/text/text-data-type.md)  
Specifies the permission values. You can specify the permissions using the syntax `<permission value>`.  

*[Optional] InherentPermissionsScope*  
&emsp;Type: [InherentPermissionsScope](../methods-auto/inherentpermissionsscope/inherentpermissionsscope-option.md)  
Specifies the scope of the permissions that are assigned (Entitlements, Permissions or Both).  

[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks

For information about the `<permission value>` syntax, refer to [permissions values](../properties/devenv-permissions-property.md#values) or [permissions on objects](../devenv-permissions-on-database-objects.md#permissions-on-objects).

## Example 

```AL
[InherentPermissions (PermissionObjectType::TableData, Database::"Customer", 'r', InherentPermissionsScope::Both)]
```

> [!NOTE]  
> Specifying `InherentPermissionsScope` is optional and the default is *Both* that includes permissions and entitlements. To read about different types of scope, see [InherentPermissionsScope Option](../methods-auto/inherentpermissionsscope/inherentpermissionsscope-option.md).

> [!NOTE]
> You can use inherent permissions only for objects within the same extension.

## See Also  
[Get Started with AL](../devenv-get-started.md)  
[Developing Extensions](../devenv-dev-overview.md)  
