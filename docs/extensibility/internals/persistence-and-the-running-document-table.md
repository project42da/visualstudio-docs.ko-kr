---
title: "지 속성 및이 실행 하는 문서 테이블 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 062c623ec1de779733e41a8abcad8ca478155dba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="persistence-and-the-running-document-table"></a>지 속성 및 실행 중인 문서 테이블
에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE, 프로젝트는 서비스를 사용 하 여을 수행할 때 해당 프로젝트 항목의 지 속성 관리를 완전히 담당 <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>합니다. 문서는 Visual Studio 환경에서 지 속성의 기본 단위입니다. 프로젝트 열기, 저장 및 실행 중인 문서 테이블 (RDT) 열려 있는 모든 문서의 상태를 추적 하는 리소스를 사용 하 여 문서의 이름 바꾸기를 조정 합니다.  
  
## <a name="managing-persistence"></a>지 속성 관리  
 프로젝트 제어를 구현 하 여 환경의 지 속성 서비스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> 인터페이스입니다. 환경에서 직접 문서를 유지할 수을 요청 하는 동안 문서를 저장할 소유 프로젝트 (또는 계층) 요청 합니다. 이렇게 하면 해당 프로젝트 항목 데이터 로컬 파일, 원격 파일, 데이터베이스, 저장소, 또는 기타 미디어를 저장 하려면 프로젝트에 대 한 합니다.  
  
 글로벌 환경에서 RDT 유지 관리합니다. 열려 있는 모든 창에 대 한 항목을 관리 하는 환경 및 문서 수 있는 하 여 RDT에 솔루션을 닫은 등의 특수 한 알림을 수신 합니다. 또한는 RDT 쉽게 처리할 수에 해당 노드와 추적 하는 환경에 대 한 **솔루션 탐색기**합니다. RDT 프로젝트 파일과 프로젝트 항목 문서를 포함 하 여 열고, 지속 개체 마다 하나의 레코드를 유지 관리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행 중인 문서 테이블](../../extensibility/internals/running-document-table.md)   
 [IDE의 선택 및 통화](../../extensibility/internals/selection-and-currency-in-the-ide.md)