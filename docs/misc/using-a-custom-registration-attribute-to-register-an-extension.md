---
title: "사용자 지정 등록 특성을 사용하여 확장 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98068fa7-bda1-4922-b3f6-28680de58c3d
caps.latest.revision: 3
caps.handback.revision: 3
manager: "douge"
---
# 사용자 지정 등록 특성을 사용하여 확장 등록
경우에 따라 사용자 지정 확장에 대 한 새 등록 속성을 작성 해야 합니다.  새 레지스트리 키를 추가 하거나 기존 키에 새 값을 추가 하려면 등록 속성을 사용할 수 있습니다.  새 속성을 파생 해야 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute>, 재정의 해야 하는 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Register%2A> 및 <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.Unregister%2A> 방법.  
  
## 사용자 지정 특성 만들기  
 다음 코드를 새 등록 속성을 작성 하는 방법을 보여 줍니다.  
  
```  
[AttributeUsage(AttributeTargets.Class, Inherited = true, AllowMultiple = false)]  
    public class CustomRegistrationAttribute : RegistrationAttribute  
    {  
    }  
  
```  
  
 <xref:System.AttributeUsageAttribute> 특성 클래스에는 관련 특성,이 두 번 이상 사용할 수 있는지 여부 및 상속 될 수 있는지 여부를 프로그램 요소 \(클래스, 메서드 등\)를 지정할 수 있습니다.  
  
### 레지스트리 키 만들기  
 다음 코드에서는 사용자 지정 특성 등록 되 있는 Vspackage를 키 아래의 사용자 하위 키를 만듭니다.  
  
```  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + @"}\Custom");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
    }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveKey(@"Packages\" + context.ComponentType.GUID + @"}\Custom");  
}  
  
```  
  
### 기존 레지스트리 키 아래 새 값 만들기  
 기존 키에 사용자 지정 값을 추가할 수 있습니다.  다음 코드는 VSPackage 등록 키에 새 값을 추가 하는 방법을 보여 줍니다.  
  
```  
public override void Register(RegistrationAttribute.RegistrationContext context)  
{  
    Key packageKey = null;  
    try  
    {   
        packageKey = context.CreateKey(@"Packages\{" + context.ComponentType.GUID + "}");  
        packageKey.SetValue("NewCustom", 1);  
    }  
    finally  
    {  
        if (packageKey != null)  
            packageKey.Close();  
                }  
}  
  
public override void Unregister(RegistrationContext context)  
{  
    context.RemoveValue(@"Packages\" + context.ComponentType.GUID, "NewCustom");  
}  
  
```