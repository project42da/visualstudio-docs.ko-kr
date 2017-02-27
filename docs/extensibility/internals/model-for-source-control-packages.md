---
title: "소스 제어 패키지에 대 한 모델 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 [Visual Studio SDK], 모델"
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 소스 제어 패키지에 대 한 모델
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 모델의 원본 컨트롤 구현 예를 나타냅니다.  모델에서 구현 해야 하는 인터페이스와 호출 해야 하는 환경 서비스를 참조 하십시오.  모든 서비스와 마찬가지로 실제로 서비스를 통해 얻은 특정 인터페이스의 메서드를 호출 합니다.  소스 제어를 수행 하는 방법를 참조 하십시오 쉽게 하는 클래스의 이름은 식별 합니다.  
  
 ![SCC&#95;TUP 예제](../../extensibility/internals/media/scc_tup.png "SCC\_TUP")  
원본 컨트롤 프로젝트 예제  
  
## 인터페이스  
 사용자 인터페이스는 다음 표에 표시 된 목록을 사용 하 여 Visual Studio 새 프로젝트 형식에 대 한 소스 제어를 구현할 수 있습니다.  
  
|Interface|사용할 도구|  
|---------------|------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|프로젝트와 편집기가 저장 또는 파일 변경 \(dirty\) 하기 전에 호출 됩니다.  이 인터페이스를 사용 하 여 액세스할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> 서비스 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|프로젝트를 추가, 제거 또는 파일 또는 디렉터리의 이름을 바꿀 수 있는 권한 요청 하 여 호출 됩니다.  이 인터페이스는 프로젝트에서 승인 된 추가, 제거 또는 작업의 이름을 바꿀 때 환경 완료 된 알려 라고도 합니다.  이 사용 하 여 액세스할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> 서비스 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|프로젝트 추가, 이름 바꾸기 또는 파일 또는 디렉터리를 제거할 때 알림을 받도록 등록 된 엔터티에 의해 구현 됩니다.  이벤트 알림을 등록 하려면 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|프로젝트는 소스 제어 패키지를 등록 하 고 소스 제어 상태에 대 한 정보를 얻기 위해 호출 됩니다.  이 인터페이스를 사용 하 여 액세스할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> 서비스 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|프로젝트 파일에 대 한 정보에 대 한 소스 컨트롤 요청에 응답 하 고 소스 제어 설정에 대 한 프로젝트 파일이 필요 얻을 수에 의해 구현 됩니다.|  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 [소스 제어를 지원합니다.](../../extensibility/internals/supporting-source-control.md)