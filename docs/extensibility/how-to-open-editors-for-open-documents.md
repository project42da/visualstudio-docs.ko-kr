---
title: "방법: 열린 문서에 대 한 편집기를 열어 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "열려 있는 문서를 열 편집기 [Visual Studio SDK]"
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: 열린 문서에 대 한 편집기를 열어
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로젝트 문서 창이 열리기 전에 프로젝트 파일의 문서 창에 다른 편집기에 열려 있는지 먼저 확인 해야 합니다.  파일을 프로젝트 고유 편집기에서 열거나 이거나 표준 편집기 중 하나를 등록 하 여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## 프로젝트 고유 편집기 열기  
 이미 열려 있는 파일에 대 한 프로젝트 고유 편집기를 열려면 다음 절차를 따르십시오.  
  
#### 열려 있는 파일에 대 한 프로젝트 고유 편집기를 엽니다.  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 메서드를 호출합니다.  
  
     이 호출 포인터 문서의 계층 구조, 계층 구조 항목 및 창 프레임에 해당 하는 경우 반환 됩니다.  
  
2.  문서가 열려 있는 경우 프로젝트 문서 데이터 개체의 존재 여부 또는 문서 뷰 개체 수도 있을 지 체크 해야 합니다.  
  
    -   문서 뷰 개체가 존재 하 고이 보기 다른 계층 또는 계층 구조 항목에 대 한 이면 프로젝트 뷰 창 프레임에 대 한 포인터를 사용 하 여 기존 창 resurface.  
  
    -   문서 뷰 개체가 존재 하 고이 보기의 동일한 계층 구조 및 계층 구조 항목에 대 한 이면 프로젝트 두 번째 보기를 열 수 있습니다이 내부 문서 데이터 개체를 연결할 수 있습니다.  그렇지 않으면 프로젝트 resurface 기존 창에 뷰 창 프레임 포인터를 사용 해야 합니다.  
  
    -   문서 데이터 개체가 있는 경우에 프로젝트의 보기에 대 한 문서 데이터 개체를 사용할 수 있는지 여부를 결정 해야 합니다.  문서 데이터 개체와 호환 되 면 완료 단계에서 설명한  [프로젝트 고유 편집기 열기](../extensibility/how-to-open-project-specific-editors.md).  
  
     문서 데이터 개체가 호환 되지 않으면 오류가 나타내는 파일에 현재 사용 중인 사용자에 게 표시 됩니다.  이 오류 파일을 동시에 컴파일하는 동안 사용자 외의 다른 편집기를 사용 하 여 파일을 열려고 시도 하는 것과 같은 일시적인 경우에만 표시 되어야의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 텍스트 편집기입니다.  코어 텍스트 편집기 컴파일러와 문서 데이터 개체를 공유할 수 있습니다.  
  
3.  문서 데이터 개체나 문서 뷰 개체가 없기 때문에 문서가 열려 있지 않은 경우 단계를 완료  [프로젝트 고유 편집기 열기](../extensibility/how-to-open-project-specific-editors.md).  
  
## 표준 편집기 열기  
 열려 이미 있는 파일에 대 한 표준 편집기를 열려면 다음 절차를 사용 합니다.  
  
#### 열려 있는 파일에 대 한 표준 편집기를 엽니다.  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>를 호출합니다.  
  
     문서를 호출 하 여 열려 있지 않은 것이 방법을 가장 먼저 확인 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>.  문서가 이미 열려 있으면 해당 편집기 창이 다시 표시 되지.  
  
2.  문서가 열려 있지 않으면 다음 단계를 완료 [방법: 표준 편집기 열기](../extensibility/how-to-open-standard-editors.md).  
  
## 참고 항목  
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 프로젝트에 특정 편집기 열기](../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 표준 편집기 열기](../extensibility/how-to-open-standard-editors.md)