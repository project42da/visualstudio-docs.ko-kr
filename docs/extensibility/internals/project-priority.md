---
title: "프로젝트 우선 순위 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "항목을 열면 프로젝트 [Visual Studio SDK]"
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 우선 순위
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 항목에는 일반적으로 솔루션에 하나의 프로젝트의 구성원입니다.  따라서, 프로젝트 항목을 여는 데 사용 되는 IDE 쉽게 확인할 수 있습니다.  항목이 두 개 이상의 프로젝트의 구성원 인 경우, IDE 우선 순위 구성표 항목을 열지에 대 한 좋은 프로젝트 사용 결정 합니다.  
  
 다음은 프로젝트 우선 순위 구성표를 보여 줍니다.  
  
-   IDE 호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> 문서에 해당 프로젝트의 멤버 인지 여부를 확인 하려면 솔루션의 각 프로젝트에 대 한 방법.  
  
-   문서 멤버는 프로젝트의 경우 프로젝트의 문서 처리에 따라 매기는 프로젝트의 우선 순위를 응답 합니다.  예를 들어, 언어 프로젝트의 언어 소스 파일에 대 한 순위가 높은 응답 하지만 빌드 프로세스의 일부로 사용 되지 않습니다에 인식할 수 없는 파일 형식에 대 한 순위가 낮은 응답 합니다.  
  
-   또한 사용자 지정, 프로젝트 고유 편집기 또는 디자이너에 대 한 문서를 제공 하는 프로젝트 높은 우선 순위를 받게 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형 우선 순위 값은 문서를 제공 합니다.  
  
-   문서를 여는 컨텍스트를 지정 하는 가장 높은 우선 순위를 지정 하는 프로젝트입니다.  두 프로젝트가 동일한 우선 순위 값을 반환 하는 경우 현재 프로젝트 사용 하는 것입니다.  문서를 열 수 없는 프로젝트를 솔루션에서 응답 하는 경우 IDE 기타 파일 프로젝트에는 문서를 만듭니다.  자세한 내용은 [기타 파일 프로젝트](../../extensibility/internals/miscellaneous-files-project.md)를 참조하십시오.  
  
## 참고 항목  
 [기타 파일 프로젝트](../../extensibility/internals/miscellaneous-files-project.md)   
 [방법: 열린 문서에 대 한 편집기를 열어](../../extensibility/how-to-open-editors-for-open-documents.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)