---
title: "우선 순위를 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: projects [Visual Studio SDK], opening items
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 51ed8cd351a306c3992b4b6c9fcc2231a90085f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="project-priority"></a>프로젝트 우선 순위
프로젝트 항목에는 일반적으로 솔루션에 프로젝트를 하나만의 구성원은 합니다. 따라서 IDE 쉽게 확인할 수 있는 프로젝트 항목을 열려면 사용 됩니다. 그러나 항목이 둘 이상의 프로젝트의 멤버인 경우 IDE는 항목을 열에 대 한 최상의 프로젝트를 확인할 우선 순위 체계를 사용 합니다.  
  
 다음 목록에는 프로젝트 우선 순위 체계를 보여 줍니다.  
  
-   IDE 호출은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> 문서 해당 프로젝트의 구성원 인지 확인 하는 솔루션의 각 프로젝트에 대 한 메서드.  
  
-   문서 프로젝트의 멤버인 경우 프로젝트 응답 우선 순위는 프로젝트의 문서 처리 능력에 따라에 할당 합니다. 예를 들어 언어 프로젝트를 우선 순위가 높은 언어 원본 파일에 대 한 응답 하지만 해당 빌드 프로세스의 일부로 사용 되지 않는 인식할 수 없는 파일 형식에 대 한 낮은 우선 순위를 사용 하 여 응답 합니다.  
  
-   또한 문서에 대 한 사용자 지정, 프로젝트 관련 편집기 또는 디자이너를 제공 하는 프로젝트는 높은 우선 순위를 받게 됩니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> 열거형 문서 우선 순위 값을 제공 합니다.  
  
-   가장 높은 우선 순위를 지정 하는 프로젝트에는 문서를 열 컨텍스트가 제공 됩니다. 두 개의 프로젝트는 우선 순위가 같은 값을 반환 하는 경우 현재 프로젝트를 사용 하는 것이 좋습니다. 솔루션의 프로젝트가 응답 문서를 열 수, 하는 경우 IDE 기타 파일 프로젝트에 문서를 저장 합니다. 자세한 내용은 참조 [기타 파일 프로젝트](../../extensibility/internals/miscellaneous-files-project.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기타 파일 프로젝트](../../extensibility/internals/miscellaneous-files-project.md)   
 [방법: 열려 있는 문서에 대 한 편집기 열기](../../extensibility/how-to-open-editors-for-open-documents.md)   
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)