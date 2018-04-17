---
title: 사용자 지정 문서 저장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- persistence, saving custom documents
- projects [Visual Studio SDK], saving custom documents
- editors [Visual Studio SDK], saving custom documents
ms.assetid: 040b36d6-1f0a-4579-971c-40fbb46ade1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5425a1c35816fd85847915029e3b6f2da1ed75a6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="saving-a-custom-document"></a>사용자 지정 문서 저장
환경 핸들의 **저장**, **다른 이름으로 저장**, 및 **모두 저장** 명령입니다. 클릭 하면 **저장**, **다른 이름으로 저장**, **또는 모두 저장** 에 **파일** 메뉴 하거나 Save All, 다음에 솔루션을 닫습니다. 프로세스가 수행 됩니다.  
  
 ![고객 편집기 저장](../../extensibility/internals/media/private.gif "개인")  
다른 이름으로 저장 하 고 모두 저장 명령 사용자 지정 편집기에 대 한 처리 저장  
  
 이 프로세스는 다음 단계에 자세히 설명 되어 있습니다.  
  
1.  에 대 한는 **저장** 및 **다른 이름으로 저장** 명령을 사용 하 여 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스는 현재 문서 창 확인 하 고 따라서 시킨 항목 저장 해야 합니다. 현재 문서 창 확인 되 면 환경을 실행 중인 문서 테이블에서 해당 문서에 계층 포인터와 항목 식별자 (itemID)를 찾습니다. 자세한 내용은 참조 [실행 중인 문서 테이블](../../extensibility/internals/running-document-table.md)합니다.  
  
     모두 저장 명령에 대 한 환경을 실행 중인 문서 테이블에서 정보를 저장 하는 모든 항목 목록이 컴파일하 사용 합니다.  
  
2.  솔루션을 받을 때는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 호출을 반복 하는 선택한 항목 집합 (즉, 다중 선택이 가능한에 의해 노출 된 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection> 서비스).  
  
3.  각 항목은 선택 영역에 대해 솔루션 포인터를 사용 하는 계층 구조를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.IsItemDirty%2A> 저장 메뉴 명령을 사용 여부를 결정 하는 메서드. 하나 이상의 항목이 더티 인 저장 명령이 사용 됩니다. 계층 표준 편집기를 사용 하는 경우 다음에 대 한 쿼리 계층 구조 대리자 커밋되지 않음 상태 편집기를 호출 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.IsDocDataDirty%2A> 메서드.  
  
4.  변경 하는 각 선택된 항목에 솔루션 포인터를 사용 하는 계층 구조를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.SaveItem%2A> 적절 한 계층에는 메서드.  
  
     사용자 지정 편집기의 경우 문서 데이터 개체 및 프로젝트 간의 통신은 private입니다. 따라서이 두 개체 간의 특별 한 지 속성 사항이 처리 됩니다.  
  
    > [!NOTE]
    >  사용자 고유의 지 속성을 구현 하는 경우 호출 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A> 시간을 절약 하는 메서드. 이 메서드는 파일을 저장할 안전 하다 있는지 확인 (예를 들어 파일이 읽기 전용이 아닌지).  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [프로젝트 항목 열기 및 저장](../../extensibility/internals/opening-and-saving-project-items.md)