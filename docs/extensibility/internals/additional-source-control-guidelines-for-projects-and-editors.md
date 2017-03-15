---
title: "프로젝트 및 편집기에 대 한 추가 소스 제어 지침 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 [Visual Studio SDK] 프로젝트와 편집기에 대 한 지침"
ms.assetid: 2483cce5-321c-4d3c-9c5c-ee8385263f74
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 프로젝트 및 편집기에 대 한 추가 소스 제어 지침
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

많은 프로젝트와 편집기에 소스 제어를 지원 하기 위해 준수 해야 하는 지침입니다.  
  
## 지침  
 또한 프로젝트 편집기에 소스 제어를 지원 하려면 다음을 수행 해야 합니다.  
  
|영역|프로젝트|편집기|설명|  
|--------|----------|---------|--------|  
|파일의 개인 복사본|X||환경 파일의 개인 복사본을 지원합니다.  즉, 프로젝트에 참여 하는 각 사용자가 자신의 개인 복사본 파일이 해당 프로젝트에 있습니다.|  
|ANSI\/유니코드 지 속성|X|X|지 속성 코드를 작성 하는 경우 대부분의 소스 제어 프로그램에서 현재 유니코드를 지원 하지 않는 때문에 ANSI 형식에서 파일 유지 됩니다.|  
|파일 열거|X||프로젝트 내에 모든 파일의 특정 목록을 포함 해야 하며 파일을 사용 하 여 목록을 열거할 수 있어야 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> \(VSH\_PROPID\_First\_Child\/Next\_Sibling\).  프로젝트 항목 이름부터도 노출 해야 그 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetMkDocument%2A> \(특수 파일 포함\) 구현 및 지원 이름 조회를 통해 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A> 구현 합니다.|  
|텍스트 형식|X|X|가능 하면 파일 텍스트 형식에서 서로 다른 버전의 병합을 지원 하도록 해야 합니다.  텍스트 형식으로 파일이 나중에 다른 버전의 파일을 병합할 수 없습니다.  기본 텍스트 형식의 XML입니다.|  
|참조를 기준으로|X||참조 기반 프로젝트에서 소스 컨트롤을 즉시 지원 됩니다.  그러나 프로젝트가 해당 파일이 디스크에 있는지 여부에 관계 없이 필요할 때, 그 파일의 목록을 만들 수 있습니다으로 디렉터리 기반 프로젝트에 소스 제어도 지원 됩니다.  소스 제어에서 프로젝트를 열 때 프로젝트 파일이 해당 파일을 먼저 다운 상태로 전환 됩니다.|  
|개체 및 속성 예상한 순서 대로 유지|X|X|파일 병합을 용이 하 게 사전순으로 같은 예측 가능한 순서 대로 유지 됩니다.|  
|다시 로드|X|X|파일이 변경 될 때 디스크 편집기를 다시 로드할 수 있어야 합니다.  소스 제어에 참여할 때의 환경 데이터를 다시 호출 하 여 로드 합니다 사용자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> 구현 합니다.  가장 어려운 로드 경우 체크 아웃 Ivsqueryeditquerysave를 호출한 경우에 발생 하는 경우입니다::<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 정보를 처리 하 고 있습니다.  그러나 다시 로드 코드를이 상황에서 실행할 수 있어야 합니다.<br /><br /> 환경에 프로젝트 파일이 자동으로 다시 로드합니다.  그러나, 프로젝트를 구현 해야 합니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> 중첩 된 경우 중첩 프로젝트 파일 다시 로드를 지원 하기 위해 계층 구조입니다.|  
  
## 참고 항목  
 [소스 제어를 지원합니다.](../../extensibility/internals/supporting-source-control.md)