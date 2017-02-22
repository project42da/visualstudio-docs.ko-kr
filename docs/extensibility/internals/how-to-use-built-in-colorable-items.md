---
title: "방법: 기본 제공 색 항목을 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "색 항목"
  - "언어 서비스, 기본 제공 색 항목"
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 기본 제공 색 항목을 사용 하 여
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기본 제공 색 항목을 사용 하기 전에 하면 먼저는 통합된 개발 환경 \(IDE\)이 경우 고유한 사용자 지정 색 항목을 제공 하 고 신호를 보내야 합니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 개체입니다.  언어 서비스에 대 한 레지스트리 항목을 설정 하 여이 작업을 수행 합니다.  
  
### 기본 제공 색 항목을 사용 하려면  
  
1.  Hkey\_local\_machine\\visualstudio\\에서*X.Y*\\Languages\\Language Services\\*언어 이름*, 어디  *X.Y* 버전의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및  *언어 이름* 이름입니다 라는 DWORD 레지스트리 항목 값을 언어를 만들기 `RequestStockColors`.  
  
2.  설정에서 `RequestStockColors` 레지스트리 항목 값을 1 합니다.  
  
     레지스트리 항목을 colorizer의 만든 후 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드 멤버를 사용할 수 있습니다에서 <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> 열거형 배열 편집기에서 색 특성을 입력 합니다.  
  
    > [!NOTE]
    >  사용자 지정 색 항목을 제공 하는 경우이 레지스트리 항목을 설정 하지 마십시오.  자세한 내용은 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)를 참조하십시오.  
  
## 참고 항목  
 [사용자 지정 편집기에서 색을 지정 하는 구문](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [구문 레거시 언어 서비스에 색 지정](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [구문 색 지정을 구현합니다.](../../extensibility/internals/implementing-syntax-coloring.md)   
 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)   
 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service2.md)