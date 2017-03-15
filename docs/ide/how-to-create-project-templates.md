---
title: "방법: 프로젝트 템플릿 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ExportTemplateWizard"
helpviewer_keywords: 
  - "프로젝트 템플릿, 만들기"
  - "프로젝트 템플릿, 사용자 지정 템플릿 위치"
  - "프로젝트 템플릿, 메타데이터 파일"
  - "Visual Studio 템플릿, 프로젝트 템플릿 만들기"
  - "Visual Studio 템플릿, 프로젝트 템플릿"
ms.assetid: a1a6999d-a34c-48a8-b1cf-027eb5c76398
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 방법: 프로젝트 템플릿 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 절차에 따라 템플릿을 .zip 파일로 패키지하는 **템플릿 내보내기** 마법사를 사용하여 템플릿을 만들 수 있습니다.  내보내기 템플릿 마법사확장명을 사용 하 여 또는 포함 된 템플릿을 사용 하 여 VSIX 파일 형식의 향상 된배포에 대 한 템플릿을만들다수도 있습니다 해당 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)], 또는 수동으로 서식 파일을만들다수 있습니다.  
  
### 표준 템플릿 내보내기 마법사를 사용하여 사용자 지정 프로젝트 템플릿을 만들려면  
  
1.  프로젝트를 만듭니다.  
  
    > [!NOTE]
    >  템플릿의 소스가 되는 프로젝트에 이름을 지정할 때 유효한 식별자 문자만 사용합니다.  잘못된 문자로 이름이 지정된 프로젝트에서 내보낸 템플릿을 사용하면 이 템플릿을 기반으로 하는 이후의 프로젝트에서 컴파일 오류가 발생할 수 있습니다.  유효한 식별자 문자에 대한 자세한 내용은 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)을 참조하십시오.  
  
2.  템플릿으로 내보낼 준비가 될 때까지 프로젝트를 편집합니다.  
  
3.  매개 변수를 대체해야 하는 위치를 나타내도록 코드 파일을 적절하게 편집합니다.  매개 변수 대체에 대한 자세한 내용은 [방법: 템플릿 매개 변수 대체](../ide/how-to-substitute-parameters-in-a-template.md)를 참조하십시오.  
  
4.  **파일** 메뉴에서 **템플릿 내보내기**를 클릭합니다.  **템플릿 내보내기** 마법사가 열립니다.  
  
5.  **프로젝트 템플릿**을 클릭합니다.  
  
6.  현재 솔루션에 프로젝트가 두 개 이상 있으면 템플릿으로 내보낼 프로젝트를 선택합니다.  
  
7.  **다음**을 클릭합니다.  
  
8.  템플릿에 대한 아이콘과 미리 보기 이미지를 선택합니다.  이러한 항목은 **새 프로젝트** 대화 상자에 나타납니다.  
  
9. 템플릿 이름 및 설명을 입력합니다.  
  
10. **마침**을 클릭합니다.  프로젝트는 .zip 파일로 내보내져 지정된 출력 위치에 배치되고, 선택된 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]로 가져올 수 있습니다.  
  
     [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]가 설치되어 있는 경우 **VSIX 프로젝트** 템플릿을 사용하여 .vsix 파일에 완성된 템플릿을 배포용으로 래핑할 수 있습니다.  자세한 내용은 [VSIX 프로젝트 템플릿을 사용 하 여 시작 하기](../extensibility/getting-started-with-the-vsix-project-template.md)를 참조하십시오.  
  
## 참고 항목  
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [방법: 항목 템플릿 만들기](../ide/how-to-create-item-templates.md)