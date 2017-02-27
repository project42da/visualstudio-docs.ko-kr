---
title: "문서 데이터와 사용자 지정 편집기에서 문서 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK]-사용자 지정 문서 데이터와 문서 보기"
ms.assetid: 71eea623-f566-4feb-84cd-ca1ba71bc493
caps.latest.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 23
---
# 문서 데이터와 사용자 지정 편집기에서 문서 보기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자 지정 편집기의 두 부분으로 구성 됩니다: 문서 데이터 개체와 문서 뷰 개체입니다. 이름으로 문서 데이터 개체 텍스트 데이터를 표시할 수 나타내고 문서 뷰 개체 \(또는 "보기"\)에 문서 데이터 개체를 표시 하는 하나 이상의 창을 나타냅니다.  
  
## 문서 데이터 개체  
 문서 데이터 개체에는 텍스트 버퍼의 텍스트 데이터 표현입니다. 문서 텍스트 및 기타 정보를 저장, 처리 문서 지 속성 및 해당 데이터의 여러 뷰를 사용 하는 COM 개체는 詳細については、次のトピックを参照してください。  
  
 <xref:EnvDTE80.Window2.DocumentData%2A>와 [문서 창](../extensibility/internals/document-windows.md)을 참조하세요.  
  
 사용자 지정 편집기 및 디자이너를 사용 하도록 설정할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체 또는 고유한 사용자 지정 하는 버퍼입니다.<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 표준 편집기에 대 한 간소화 된 포함 모델을 따르며, 여러 뷰를 지원 하 고 여러 뷰를 관리 하는 데 사용 되는 이벤트 인터페이스를 제공 합니다.  
  
## 문서 뷰 개체  
 코드 및 기타 텍스트를 표시 하는 창을 문서 라고 보기 또는 보기입니다. 편집기를 만들 때에 하나의 창에서 텍스트는 표시 되는 단일 뷰를 또는 텍스트가 둘 이상의 창에 표시 되는 여러 뷰를 선택할 수 있습니다. 선택한 응용 프로그램에 따라 달라 집니다. 예를 들어 side\-by\-side\-편집에 필요한 경우에 여러 보기를 선택 합니다. 각 보기는 통합된 개발 환경에서의 \(IDE\) document 테이블 \(RDT\)를 실행 중인 항목에 연관 됩니다. 프로젝트에 속하는 보기 창 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 개체입니다.  
  
 편집기에서 문서 데이터 개체의 여러 뷰를 지 원하는 경우 다음 문서 데이터와 문서 보기 개체 구분 되어야 합니다. 그렇지 않으면 이러한 그룹화 할 수 있습니다. 자세한 내용은 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)을 참조하세요.  
  
 IDE에 실행 중인 문서 테이블의 각 항목에 대 한 항목 식별자 \(ItemID\)를 비교 하 여 \(예: 문서를 포함 하는 솔루션을 닫으면\) 이벤트에 대 한 뷰를 알립니다. 이에 대한 자세한 내용은 [실행 중인 Document 테이블](../extensibility/internals/running-document-table.md)를 참조하세요.  
  
 사용자 지정 편집기에 대 한 보기를 만드는 방법은 두 가지가 있습니다. 하나는 내부 활성화 모델을 보기 ActiveX 컨트롤 또는 문서 데이터 개체를 사용 하 여 창에서 호스트 되는 위치입니다. 두 번째는 보기에서 호스트 되는 위치, 단순화 된 포함 모델 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 창 명령을 처리 하기 위해 구현 됩니다. 내부 활성화 모델에 대 한 정보를 참조 하십시오. [현재 위치에서 활성화](../misc/in-place-activation.md)합니다. 단순화 된 포함 모델에 대 한 정보를 참조 하십시오. [간단한 포함](../extensibility/simplified-embedding.md)합니다.  
  
## 참고 항목  
 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)   
 [간단한 포함](../extensibility/simplified-embedding.md)   
 [방법: 뷰 문서 데이터를 연결 합니다.](../extensibility/how-to-attach-views-to-document-data.md)   
 [문서 잠금 소유자 관리](../extensibility/document-lock-holder-management.md)   
 [단일 및 다중 탭 뷰](../extensibility/single-and-multi-tab-views.md)   
 [표준 문서 저장](../extensibility/internals/saving-a-standard-document.md)   
 [지 속성 및 실행 Document 테이블](../extensibility/internals/persistence-and-the-running-document-table.md)   
 [프로젝트의 파일 편집기 열리는 결정합니다.](../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)   
 [편집기 팩터리](../extensibility/editor-factories.md)