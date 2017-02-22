---
title: "문자 모양 제어 (소스 제어 VSPackage) | Microsoft Docs"
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
  - "소스 제어 패키지 문자 모양"
  - "소스 제어 패키지, 문자 모양"
ms.assetid: b9413b08-b3c3-4fc3-a6e0-3dc0db3652d7
caps.latest.revision: 20
caps.handback.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
---
# 문자 모양 제어 (소스 제어 VSPackage)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 Vspackages에 사용할 수 있는 통합 되어 일부 소스 제어 항목의 상태를 나타내는 고유한 문자 모양을 표시 하는 기능입니다.  
  
## 수준의 문자 모양 제어  
 예제에 표시 된 항목의 현재 상태를 나타내는 아이콘과 상태 모양입니다  **솔루션 탐색기** 또는  **클래스 뷰**.  소스 제어 VSPackage 두 문자 모양 제어 수준을 발휘할 수 있습니다.  선택은 미리 정의 된 집합에 제공 되는 문자 모양 글리프를 제한할 수 있습니다에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에는 일련의 문자 모양 표시 하 정의할 수 있습니다.  
  
### 기본 문자 집합  
 항목에 연결 된 상태로 문자 모양 결정 합니다  **솔루션 탐색기**, 컨트롤 소스를 사용 하 여에서 프로젝트 상태 기호 요청은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.GetSccGlyph%2A>.  소스 제어 VSPackage 유지 IDE에서 제공 하는 미리 정의 된 문자 모양에 국한 된 글리프를 선택할 수도 있습니다.  이 경우 있는 VSPackage 다시 vsshell.idl에 정의 된 글리프 열거 형식을 나타내는 값의 배열을 전달 합니다.  자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon> .이 문자 모양의 "체크 인" 모양 및 확인 표시 "체크 아웃" 모양으로 자물쇠와 같은 IDE를 설정할 미리 정의 된 집합입니다.  
  
### 사용자 지정 문자 모양을 설정  
 설치 될 때 소스 제어 Vspackage는 고유한 "디자인에 대 한" 고유한 문자 모양을 사용할 수 있습니다.  새 소스 제어 VSPackage 활성화 되 면 자체 글리프 VSPackage 이전 소스 제어 경우에 여전히 로드를 사용 하 여 시작할 수 있지만 비활성화 해야 합니다.  이 모드에서는 소스 제어 VSPackage 여전히 기존 아이콘 모양을 일관성을 유지 하기 위해 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 선택한 경우입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> 서비스 인터페이스를 지 원하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>, 어떤 Vspackage를 구현할 수 있습니다 \(선택 사항\)과 됩니다 수에 대 한 IDE에서.  IDE에서 요청 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 차례로 VSPackage 현재 등록 된 원본 컨트롤에서이 인터페이스를 가져올 시도 합니다.  인터페이스 등록 된 Vspackage에 존재 하는 경우 사용자 지정 문자 모양에 대 한 요청에서 IDE의 성공. 그렇지 않은 경우는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 사용 하 여 기본 설정 된 문자 모양입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs.GetCustomGlyphList%2A> 메서드를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다양 한 소스 제어를 보여주는 이미지 목록을 얻을 수 없다는.  소스 제어 VSPackage IDE로 이미지 목록에서 사용자 지정 문자 모양에 대 한 핸들을 반환합니다.  IDE 이미지 목록의 복사본이 됩니다 하이 나중에 표시할 글리프를 선택 합니다.  새로운 인터페이스 지원 되지 않는 경우 또는 해당 `IVsSccGlyphs::GetCustomGlyphList` 메서드는 E\_NOTIMPL을 반환 IDE에서 제공 된 문자 모양의 기본 목록에서 해당 문자를 가져오고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>