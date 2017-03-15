---
title: "방법: 뷰 문서 데이터를 연결 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK]-사용자 지정 뷰 문서 데이터 연결"
ms.assetid: f92c0838-45be-42b8-9c55-713e9bb8df07
caps.latest.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 22
---
# 방법: 뷰 문서 데이터를 연결 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

새 문서 보기를 설정한 경우 기존 문서 데이터 개체에 연결할 수 있습니다.  
  
### 기존 문서 데이터 개체에 뷰를 연결할 수 경우를 확인 하려면  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>를 구현해야 합니다.  
  
2.  구현에서 `IVsEditorFactory::CreateEditorInstance`, 호출 `QueryInterface` IDE를 호출할 때 기존 문서 데이터 개체에 대 여 `CreateEditorInstance` 구현 합니다.  
  
     호출 `QueryInterface` 에 지정 된 기존 문서 데이터 개체를 검사할 수 있습니다는 `punkDocDataExisting` 매개 변수입니다.  
  
     그러나 다른 설명이 없는 4 단계에 설명 된 대로 검색 해야 하는 정확한 인터페이스는 문서를 열 편집기 따라 달라 집니다.  
  
3.  기존 문서 데이터 개체에 대 한 적절 한 인터페이스를 찾을 수 없는 오류 코드 편집기와 호환 되는 문서 데이터 개체 아님을 나타내는 편집기를 반환 합니다.  
  
     IDE의 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, 메시지 상자를 알립니다 문서 다른 편집기에 열려 묻는를 닫습니다.  
  
4.  이 문서를 닫으면 Visual Studio를 한 번에 대 한 편집기 팩터리를 호출 합니다. 이 호출에는 `DocDataExisting` 매개 변수는 null입니다. 편집기 팩터리 구현을 사용자 고유의 편집기에서 문서 데이터 개체를 열 수 있습니다.  
  
    > [!NOTE]
    >  를 기존 문서 데이터 개체에서 작업할 수 있는지 여부를 확인 하려면 사용할 수도 있습니다 인터페이스 구현의 개인 정보는 실제에 대 한 포인터를 캐스팅 하 여 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 개인 구현의 클래스입니다. 예를 들어 모든 표준 편집기 구현 `IVsPersistFileFormat`, 에서 상속한 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist>합니다. 따라서 호출할 수 있습니다 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist.GetClassID%2A>, 기존 문서 데이터 개체의 클래스 ID 구현와 일치 하는 경우 클래스 ID, 다음 문서 데이터 개체를 사용 하 여 작업할 수 있습니다.  
  
## 강력한 프로그래밍  
 Visual Studio의 사용자 구현을 호출 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 메서드를 다시 대 한 포인터를 전달에서 기존 문서 데이터 개체는 `punkDocDataExisting` 매개 변수가 있는 경우. 반환 되는 문서 데이터 개체를 검사 `punkDocDataExisting` 문서 데이터 개체를이 항목의 절차의 4 단계에 나와 있는 참고에 설명 된 대로 편집기에 대 한 적절 한 경우를 확인 합니다. 수준이 적절 하 게 하는 경우에 설명 된 대로 편집기 팩터리는 데이터에 대 한 두 번째 보기 제공 해야 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)합니다. 그렇지 않으면 적절 한 오류 메시지가 표시 되어야 합니다.  
  
## 참고 항목  
 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)   
 [문서 데이터와 사용자 지정 편집기에서 문서 보기](../extensibility/document-data-and-document-view-in-custom-editors.md)