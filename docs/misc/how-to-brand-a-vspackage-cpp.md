---
title: "방법: VSPackage 브랜딩(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "정보 대화 상자"
  - "VSPackage, 시작 화면"
  - "VSPackage, 브랜딩"
ms.assetid: a1b9213f-8702-4716-8623-cd3705d531fa
caps.latest.revision: 10
caps.handback.revision: 10
manager: "douge"
---
# 방법: VSPackage 브랜딩(C++)
에  **도움말** 대화 상자 및 시작 화면, Vspackages를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct> 인터페이스입니다.  이렇게 하려면 다음 정보를 제공 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   Name  
  
-   직렬 포트 또는 버전 번호와 같은 ID  
  
-   정보  
  
-   로고 아이콘  
  
 `IVsInstalledProductImpl` 클래스는 해당 정보에 대 한 템플릿 매개 변수를 사용 합니다.  각 템플릿 매개 변수는 ID입니다.  처음 세 개의 문자열 리소스 id가 고 네 번째 아이콘의 리소스 ID입니다.  
  
## 예제  
 다음과 같은 클래스 선언을 VSPackage 클래스에 대 한 것은 [VSSDK 샘플](../misc/vssdk-samples.md).  
  
```  
class ATL_NO_VTABLE BasicPackage :   
  ...  
  public IVsInstalledProductImpl<  
    IDS_BASICPACKAGE_PRODUCT_NAME,  
    IDS_BASICPACKAGE_PRODUCT_IDENTIFIER,   
    IDS_BASICPACKAGE_PRODUCT_DETAILS,   
    IDI_BASICPACKAGE_LOGO>  
```  
  
 Vspackage를 테스트 하기를 참조 하십시오 [방법: 도움말 정보 및 시작 화면 테스트](../misc/how-to-test-the-help-about-and-splash-screens.md).  
  
## 참고 항목  
 [VSPackage 브랜딩](../misc/vspackage-branding.md)