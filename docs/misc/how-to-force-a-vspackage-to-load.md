---
title: "방법: VSPackage 강제 로드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSPackage, 강제 로드"
  - "VSPackage, 로드"
ms.assetid: 05f4dc3f-3c9a-45ea-96da-986553b5c5f2
caps.latest.revision: 20
caps.handback.revision: 20
manager: "douge"
---
# 방법: VSPackage 강제 로드
만 함께 제공 되는 기능은 프로세스를 완료 하려면 필요한 경우 VSPackages 일반적으로 로드 됩니다.  그러나 경우에 따라 Vspackage를 강제로 다른 VSPackage 로드 되도록 할 수 있습니다.  예를 들어, 경량 Vspackage는 Cmduicontext로 사용할 수 있는 프로그래밍 컨텍스트는 큰 VSPackage 로드 합니다.  
  
 사용할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A> 메서드는 VSPackage 로드.  
  
### 있는 VSPackage 로드를 강제로  
  
-   이 코드에 삽입은 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 의 다른 VSPackage 로드 하려면 강제로 VSPackage 메서드:  
  
     [!code-cs[ForceVSPackageLoad#01](../misc/codesnippet/CSharp/how-to-force-a-vspackage-to-load_1.cs)]  
  
     있는 VSPackage 초기화 되 면 강제로 `PackageToBeLoaded` 를 로드할 수 있습니다.  
  
## 강력한 프로그래밍  
 강제 로드 VSPackage 통신에 사용할 수 없습니다.  대신 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)를 사용하십시오.  
  
## 참고 항목  
 [Vspackage를 관리합니다.](../extensibility/managing-vspackages.md)   
 [Vspackage](../extensibility/internals/vspackages.md)