---
title: "방법: 새 프로젝트 대화 상자에 템플릿 추가 | Microsoft Docs"
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
  - "대화 상자, 프로젝트에 템플릿 추가"
  - "프로젝트[Visual Studio SDK], 대화 상자에 템플릿 추가"
  - "템플릿[Visual Studio], 프로젝트 대화 상자에 추가"
ms.assetid: fd044681-e666-410d-815c-33db923ed888
caps.latest.revision: 26
caps.handback.revision: 26
manager: "douge"
---
# 방법: 새 프로젝트 대화 상자에 템플릿 추가
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설치 중 미리 정의된 많은 프로젝트 템플릿이 설치됩니다. 미리 정의된 프로젝트 템플릿의 전체 목록은 [NIB 템플릿에서 프로젝트 만들기](http://msdn.microsoft.com/ko-kr/7c36d86a-6b79-4480-8228-0f925f1204b2)를 참조하세요. 기본 프로젝트 템플릿 외에 사용자 지정 또는 하위 형식별 프로젝트 템플릿을 만들 수 있습니다. 예를 들어 **스마트 장치** 하위 형식에는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트에 대한 템플릿이 제공됩니다. 사용자 지정 템플릿을 만드는 방법에 대한 자세한 내용은 [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)을 참조하세요.  
  
## 새 프로젝트 대화 상자에 템플릿 추가  
  
#### 새 프로젝트 대화 상자에 템플릿을 추가하려면  
  
1.  MyTemplate.vstemplate 파일을 포함하는 템플릿을 만듭니다.  
  
2.  템플릿\(.vstemplate 파일 포함\)에 있는 파일을 선택하고 마우스 오른쪽 단추로 클릭한 다음 **보내기**를 클릭하고 **압축\(ZIP\) 폴더**를 클릭합니다. 이전에 추출한 파일을 .zip 파일로 압축합니다.  
  
 .zip 템플릿 파일을 **%USERPROFILE%\\Documents\\Visual Studio 2015\\Templates\\ProjectTemplates**에 넣습니다.  
  
## 참고 항목  
 [Project Subtypes](d235b47b-cf11-4d47-a63f-e33d9d16105d2044a030-0795-4940-bd65-a6e44de98a0f)   
 [NIB: Visual Studio 템플릿](http://msdn.microsoft.com/ko-kr/141fccaa-d68f-4155-822b-27f35dd94041)   
 [기여 하는 새 항목 추가 대화 상자](../extensibility/internals/contributing-to-the-add-new-item-dialog-box.md)