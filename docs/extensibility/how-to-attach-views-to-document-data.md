---
title: '방법: 뷰 문서 데이터에 연결 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - attach views to document data
ms.assetid: f92c0838-45be-42b8-9c55-713e9bb8df07
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e3dfe0163bc4a47ec51e5c2dea832f6adda42ff7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-attach-views-to-document-data"></a>방법: 뷰 문서 데이터를 연결 합니다.
새 문서 보기를 설정한 경우 기존 문서 데이터 개체에 연결할 수 있습니다.  
  
### <a name="to-determine-if-you-can-attach-a-view-to-an-existing-document-data-object"></a>기존 문서 데이터 개체에 뷰를 연결할 수 경우를 확인 하려면  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>를 구현해야 합니다.  
  
2.  구현에서 `IVsEditorFactory::CreateEditorInstance`, 호출 `QueryInterface` IDE를 호출할 때 기존 문서 데이터 개체에 사용자 `CreateEditorInstance` 구현 합니다.  
  
     호출 `QueryInterface` 에 지정 된 기존 문서 데이터 개체를 검사할 수 있습니다는 `punkDocDataExisting` 매개 변수입니다.  
  
     그러나 다른 설명이 없는 4 단계에 설명 된 대로 검색 해야 하는 정확한 인터페이스는 문서를 열 편집기에 따라 다릅니다.  
  
3.  기존 문서 데이터 개체에 대 한 적절 한 인터페이스를 찾을 수 없는 문서 데이터 개체로 편집기와 호환 되는지 나타내는 편집기에 오류 코드를 반환 합니다.  
  
     IDE의 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, 문서가 다른 편집기에에서 열려 있는 이므로 닫을 것인지 묻는 메시지 상자 알립니다 있습니다.  
  
4.  이 문서를 닫으면 Visual Studio를 한 번에 대 한 편집기 팩터리를 호출 합니다. 이 호출의 `DocDataExisting` 매개 변수는 null입니다. 편집기 팩터리 구현 사용자 고유의 편집기에서 문서 데이터 개체로 열 수 있습니다.  
  
    > [!NOTE]
    >  기존 문서 데이터 개체로 작업할 수 있는지를 확인 하려면 사용할 수도 있습니다 인터페이스 구현의 개인 정보는 실제에 대 한 포인터를 캐스팅 하 여 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 개인 구현 클래스입니다. 예를 들어 모든 표준 편집기 구현 `IVsPersistFileFormat`에서 상속한 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist>합니다. 따라서 호출할 수 있습니다 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist.GetClassID%2A>, 기존 문서 데이터 개체의 클래스 ID 암호와 일치 하는지를 구현 클래스 ID, 다음 문서 데이터 개체로 작업할 수 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 Visual Studio의 사용자 구현을 호출 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드를 다시 대 한 포인터에 전달 된 기존 문서 데이터 개체는 `punkDocDataExisting` 있는 경우 매개 변수입니다. 문서 데이터 개체에 반환 된 검사 `punkDocDataExisting` 문서 데이터 개체로 편집기가이 항목의 절차의 4 단계에 나와 있는 참고에 설명 된 대로에 적합 한지 확인 하려면. 수준이 적절 하 게 다음에 설명 된 대로 편집기 팩터리 데이터에 대 한 두 번째 뷰를 제공 해야 하는 경우 [여러 문서 보기를 지 원하는](../extensibility/supporting-multiple-document-views.md)합니다. 그렇지 않은 경우 적절 한 오류 메시지를 표시 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)   
 [사용자 지정 편집기의 문서 데이터 및 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md)