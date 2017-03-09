---
title: "브랜딩 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
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
ms.assetid: a47b3645-574c-41c7-8a97-d071cd6b1e82
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# 브랜딩 개요
시작 화면에서 제품 정보를 표시 하려면 또는  **도움말** 대화 상자를 VSPackage 해야 중 하나:  
  
-   InstalledProducts 레지스트리 키에서 자세한 제품 정보를 제공 합니다.  
  
     또는  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct>를 구현합니다.  
  
 패키지 관리 프레임 워크 \(MPF\) 제공의 <xref:Microsoft.VisualStudio.Shell.InstalledProductRegistrationAttribute> InstalledProducts 레지스트리 키 아래 등록을 제어 하는 특성입니다.  자세한 내용은 [방법: VSPackage 브랜딩\(C\# 및 Visual Basic\)](../misc/how-to-brand-a-vspackage-csharp-and-visual-basic.md)를 참조하십시오.  
  
 Visual Studio 라이브러리를 제공의 `IVsInstalledProductImpl` 템플릿 클래스의 구현을 만드는 데 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct>.  자세한 내용은 [방법: VSPackage 브랜딩\(C\+\+\)](../misc/how-to-brand-a-vspackage-cpp.md)를 참조하십시오.  
  
 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct> 명시적으로 특성 또는 서식 파일을 사용 하 여 보다 더 강력한 것입니다.  
  
-   다른 시작 화면 아이콘을 지정할 수 있습니다에서  **도움말** 아이콘.  
  
-   다른 시작 화면 제품 이름을 지정할 수 있습니다에서  **도움말** 제품 이름.  
  
    > [!IMPORTANT]
    >  사용 하는 경우 <xref:Microsoft.VisualStudio.Shell.InstalledProductRegistrationAttribute> 와 함께 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct>, 인터페이스 우선 순위를 갖습니다.  
  
    > [!NOTE]
    >  다음과 같은 시작 화면을 사용 하 여  **도움말** 대화 상자.  시작 화면에는 16 × 16 이미지 및 32 × 32 이미지를 VSPackage 아이콘 리소스를 포함 해야의  **도움말** 대화 상자.  하나의 이미지 크기를 제공 하는 경우 필요에 따라 조정 됩니다 있지만 표시 결과 최적이 아닌 수 있습니다.  
  
 관련된 작업 목록을 참조 하십시오. [Vspackage](../extensibility/internals/vspackages.md).  
  
## 참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)   
 [Visual Studio 라이브러리 개요](../misc/visual-studio-library-overview.md)