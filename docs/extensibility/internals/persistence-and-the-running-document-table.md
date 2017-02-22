---
title: "지 속성 및 실행 Document 테이블 | Microsoft Docs"
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
  - "지 속성 관리"
  - "IVsPersistHierarchyItem 인터페이스 구현"
  - "아키텍처, 지 속성"
  - "실행 중인 document 테이블 (RDT) 아키텍처"
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 지 속성 및 실행 Document 테이블
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE, 프로젝트는 서비스를 사용 하 여 달성 하는 프로젝트 항목, 유지 관리를 완전히 담당 <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>합니다. 문서는 Visual Studio 환경에서 지 속성의 기본 단위입니다. 프로젝트 열기, 저장 및 실행 문서 테이블 \(RDT\) 열린 문서 모두의 상태를 추적 하는 리소스를 사용 하 여 문서의 이름을 조정 합니다.  
  
## 지 속성 관리  
 프로젝트의 환경 지 속성 서비스를 구현 하 여 제어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> 인터페이스입니다. 환경에서 직접 문서를 유지할 수을 요청 하는 동안은 소유 프로젝트 \(또는 계층\) 문서를 저장할 요청 합니다. 그러면 프로젝트 항목 데이터의 로컬 파일, 원격 파일, 데이터베이스, 저장소, 또는 기타 미디어를 저장 하려면 프로젝트에 대 한 수 있습니다.  
  
 전역 환경에는 RDT 유지 관리합니다. 열려 있는 모든 창에 대 한 항목을 관리 하는 환경 및 할 수 있도록 하는 RDT의 문서 솔루션을 닫을 때와 같은 특수 한 알림을 수신 합니다. 또한는 RDT 있기 때문에 해당 노드와 추적 하는 환경에 대 한 **솔루션 탐색기**합니다. RDT 프로젝트 파일과 프로젝트 항목 문서를 포함 하 여 열고, 지속 개체 마다 하나의 레코드를 유지 관리 합니다.  
  
## 참고 항목  
 [실행 중인 Document 테이블](../../extensibility/internals/running-document-table.md)   
 [선택 및 IDE에서 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)