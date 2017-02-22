---
title: "소스 제어 디자인 결정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 [Visual Studio SDK] 디자인 결정"
ms.assetid: 5f60ec1a-5a74-4362-8293-817a4dd73872
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 디자인 결정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디자인 결정 한 다음 프로젝트에 대해 소스 제어를 구현 하는 경우 고려해 야 합니다.  
  
## 정보 공유 또는 개인 수 있습니까?  
 가장 중요 한 디자인 결정 수 있습니다 어떤 정보를 공유할 수 있습니다와 개인입니다.  예를 들어, 프로젝트 파일 목록을 공유 했지만이 파일 목록 내의 일부 사용자 개인 파일 할 수 있습니다.  컴파일러 설정을 공유 하는, 하지만 시작 프로젝트는 일반적으로 전용입니다.  설정 순전히 공유, 공유 된 재정의 또는 순전히 개인입니다.  사용자 솔루션 파일 \(.suo\)을 옵션으로 의도적으로 개인 항목에 체크 되지 않은 [!INCLUDE[vsvss](../../extensibility/includes/vsvss_md.md)].  .Suo 파일 또는 만드는, 예를 들어, 특정 개인 파일 등과 같은 개인 파일에는 개인 정보를 저장 해야 합니다.는. csproj.user 파일에 대 한 Visual C\# 나는. vbproj.user 파일 Visual Basic 대 한.  
  
 이 결정 일부를 보여 줍니다 및 항목\-기반을 만들 수 있습니다.  
  
## 프로젝트 특별 한 파일이 포함 됩니다.  
 또 다른 중요 한 설계 결정 프로젝트 구조를 특수 파일을 사용 하는지 여부입니다.  특수 파일 표시 솔루션 탐색기와 체크 인 및 체크 아웃 대화 상자 파일 기본이 되는 숨김된 파일입니다.  특별 한 파일을 사용 하는 경우 다음이 지침을 따르십시오.  
  
1.  특수 파일 프로젝트 루트 노드와 연결 되지\-즉, 프로젝트를 자체 파일입니다.  프로젝트 파일을 하나의 파일에 있어야 합니다.  
  
2.  특수 파일 추가, 제거 하거나 프로젝트에 적절 한 이름을 변경할 때 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2> 파일은 특정 파일을 나타내는 플래그 집합으로 이벤트가 발생 합니다.  이러한 이벤트는 환경에 적절 한 호출 하는 프로젝트에 대 한 응답으로 호출 됩니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 메서드가 있습니다.  
  
3.  때 프로젝트 또는 편집기를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 파일을 해당 파일과 관련 된 특수 한 파일이 자동으로 체크 아웃 되지 않은.  특수 파일의 부모 파일에 전달 합니다.  환경 관계 사이 전달 되는 모든 파일을 검색 하 고 적절 하 게 체크 아웃 UI에 특수 한 파일을 숨기기 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [소스 제어를 지원합니다.](../../extensibility/internals/supporting-source-control.md)