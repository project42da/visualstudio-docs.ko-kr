---
title: "사용자 지정 작업 목록 보기 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "작업 목록, 사용자 지정 보기"
ms.assetid: c25f8f5d-55a1-4b5e-b617-3d1140bcb98a
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# 사용자 지정 작업 목록 보기 만들기
사용자 지정 작업 목록 뷰를 작성 하 여 사용자 지정 작업 목록에서 Visual Studio 표시할 수 있습니다.  
  
 레지스트리를 사용 하 여 사용자 지정 보기를 만들고 이러한 사양을 확인 합니다.  
  
-   열  
  
-   열에 대해 정렬 순서  
  
-   기본 정렬 순서  
  
-   표시 작업 범주  
  
 사용자 지정 범주를 표시 하거나 CAT\_ALL 여러 개의 범주를 지정할 수 있습니다.  텍스트를 포함 하는 사용자 정의 텍스트 열을 만들 수도 있습니다.  그러나 사용자 지정 텍스트 열을 정렬할 수 없습니다.  
  
 다음 표의 레지스트리 형식 지정 작업 목록 뷰를 표시합니다.  
  
 테이블, 테이블의 각  *VS Reg 루트* 에 hkey\_local\_machine\\software\\microsoft\\visualstudio\\8.0\\과 같습니다.  각 레지스트리 문에 대 한 추가 정보 및 스크립트 항목 테이블을 제공합니다.  
  
 *VS Reg 루트*\\TaskList\\Views\\*GUID*  
  
|Name|형식|범위|설명|  
|----------|--------|--------|--------|  
|Name|REG\_SZ|Text|보기 또는 \# xxx의 문자열 이름입니다.<br /><br /> 이름을 "내 사용자 지정 보기"와 같은 일반 문자열 수 또는 리소스 문자열 \# \(xxx\) 패키지 내에서 사용할 수 있습니다.|  
|패키지|REG\_SZ|Text|\[선택\] GUID의 문자열 표현입니다.  문자열 리소스 문자열 \(\# xxx\);는 경우에 필수입니다. 그렇지 않은 경우 무시 됩니다.|  
  
 *VS Reg 루트*\\TaskList\\Views\\*GUID*\\Columns\\*수*  
  
> [!NOTE]
>  *번호* \(여기서 1은 맨 왼쪽 열\) 보기의 열 1에 따른 순서입니다.  더 많은 열을 증가 시킬  *번호*.  
  
|Name|형식|범위|설명|  
|----------|--------|--------|--------|  
|필드|REG\_DWORD||A <xref:Microsoft.VisualStudio.Shell.Interop.VSTASKFIELD> 열의 필드입니다.|  
|너비|REG\_DWORD||선택적 요소.  열의 너비\(픽셀\)입니다.  열이 많은 경우이 매개 변수가 무시 됩니다.|  
|Index|REG\_DWORD||선택적 요소.  FLD\_CUSTOM 필드인 경우, 사용자 지정 열 인덱스입니다.|  
|Name|REG\_SZ|Text|FLD\_CUSTOM 필드인 경우,이 사용자 지정 열의 이름입니다.<br /><br /> 이름 리소스 문자열 \# xxx 형식이 될 수도 있습니다.|  
|Filter|REG\_DWORD 또는 REG\_SZ||기본 제공 VSTASKCATEGORY 또는 사용자 정의 범주의 GUID를 나타내는 문자열 중 하나는 DWORD입니다.|  
  
 *VS Reg 루트*\\TaskList\\Views\\*GUID*\\Sort\\*수*  
  
> [!NOTE]
>  *번호* 정렬 키를 식별 합니다.  기본 정렬 키에 대 한 예를 들어,  *수* 1과 같습니다.  보조 정렬 키에 대 한  *수* 2 등과 같습니다.  
  
|Name|형식|범위|설명|  
|----------|--------|--------|--------|  
|필드|REG\_DWORD||A <xref:Microsoft.VisualStudio.Shell.Interop.VSTASKFIELD> 열의 필드입니다.|  
|Index|REG\_DWORD||선택적 요소.  FLD\_CUSTOM 필드인 경우, 사용자 지정 열 인덱스입니다.|  
  
 열 사용자 지정을 구현 하려면 반드시 구현 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2> 인터페이스를 작업 항목에 인터페이스에 다음 메서드를 구현 해야 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.get_CustomColumnText%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.put_CustomColumnText%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2.IsCustomColumnReadOnly%2A>  
  
 필요한 경우 작업 목록 쿼리를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem2> 에서 표시 되는 특정 보기를 사용자 지정 열 번호를 사용 하 여 구현  *일부 guid*.  작업 보기에서 해당 열에 대 한 적절 한 정보가 있으면 해당 열에 대 한 정보를 제공 하 고 해당 텍스트가 읽기 전용인 지 여부를 지정 합니다.  
  
## 참고 항목  
 [방법: 작업 목록의 사용자 지정 범주 만들기](../misc/how-to-create-custom-categories-of-task-lists.md)