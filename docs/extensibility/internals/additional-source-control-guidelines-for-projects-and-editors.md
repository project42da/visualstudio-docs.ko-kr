---
title: "프로젝트 및 편집기에 대 한 추가 소스 제어 지침 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], guidelines for projects and editors
ms.assetid: 2483cce5-321c-4d3c-9c5c-ee8385263f74
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 308de182e604f06fff9ad25cb65428b2d48ff257
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="additional-source-control-guidelines-for-projects-and-editors"></a>프로젝트 및 편집기에 대 한 추가 소스 제어 지침
프로젝트 및 편집기를 소스 제어를 지원 하기 위해 준수 해야 하는 지침의 여러 가지가 있습니다.  
  
## <a name="guidelines"></a>지침  
 프로젝트 또는 편집기 소스 제어를 지원 하려면 다음을 수행 해야 합니다.  
  
|영역|프로젝트|편집기|설명|  
|----------|-------------|------------|-------------|  
|파일의 개인 복사본이|X||환경에서 파일의 개인 복사본이 지원 합니다. 즉, 프로젝트에 참여 하는 각 사용자에 해당 프로젝트에 있는 파일의 직접 자신의 개인 복사본입니다.|  
|ANSI/유니코드 지 속성|X|X|지 속성 코드를 작성 하는 경우 대부분의 소스 제어 프로그램은 현재 유니코드를 지원 하지 않으므로 ANSI 형식으로 파일을 유지 합니다.|  
|파일을 열거|X||프로젝트 내의 모든 파일의 특정 목록을 포함 해야 하 고 사용 하 여 파일의 목록을 열거할 수 있어야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (VSH_PROPID_First_Child/Next_Sibling). 프로젝트 항목 이름을 통해 또한 제공 해야 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.GetMkDocument%2A> 구현 및 지원 이름 조회 (특수 한 파일 포함)를 통해 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.IsDocumentInProject%2A> 구현 합니다.|  
|텍스트 형식|X|X|가능 하면 서로 다른 버전의 병합을 지원 하도록 텍스트 형식 파일 이어야 합니다. 텍스트 형식에 없는 파일을 파일의 다른 버전과 함께 나중에 병합할 수 없습니다. 기본 텍스트 형식은 XML입니다.|  
|기반 참조|X||프로젝트 기반 참조 쉽게 소스 제어에 사용할 수 있습니다. 그러나 디렉터리 기반 프로젝트는 지원 소스 제어로으로 프로젝트에 해당 파일이 디스크에 있는지 여부에 관계 없이 필요에 따라 해당 파일의 목록을 생성할 수 있습니다. 소스 제어에서 프로젝트를 열 때 프로젝트 파일의 모든 파일 하기 전에 먼저 상태로 전환 됩니다.|  
|예측 가능한 순서로 개체 및 속성을 유지|X|X|병합을 용이 하 게 하려면 사전순으로 같은 예측 가능한 순서로 프로그램 파일을 유지 합니다.|  
|다시 로드|X|X|디스크에서 파일 변경 되 면 편집기 다시 로드 수 있어야 합니다. 소스 제어에 참가 하는 경우 환경은 데이터를 다시 로드를 호출 하 여 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> 구현 합니다. 가장 어려운 다시 로드 경우는 체크 아웃 IVsQueryEditQuerySave를 호출 했을 때 발생 하는 경우::<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 정보를 처리 하 고 있습니다. 그러나 다시 로드 코드 이러한 상황에서 실행할 수 있어야 합니다.<br /><br /> 환경에는 자동으로 프로젝트 파일 다시 로드합니다. 그러나 프로젝트를 구현 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2> 계층을 다시 로드를 지원 하기 위해 중첩 프로젝트 파일에 중첩 된 경우.|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)