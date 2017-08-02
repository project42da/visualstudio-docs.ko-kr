---
title: "레거시 API를 사용 하 여 텍스트 버퍼에 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-텍스트 버퍼"
ms.assetid: cd6cf4ae-fff5-4e23-b293-7cbafdb8aed2
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# 레거시 API를 사용 하 여 텍스트 버퍼에 액세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트를 텍스트 스트림, 파일 지 속성을 관리 하는 데 담당 합니다.  버퍼 읽거나 다른 형식을 쓸 수 있지만, 모든 일반적인 통신 버퍼에 유니코드를 사용 하 여 수행 됩니다.  레거시 Api에 텍스트 버퍼 1\-또는 2 차원 좌표계 버퍼에 있는 문자 위치를 식별 수 있습니다.  
  
## 1 및 2 차원 좌표계  
 1 차원 좌표 위치에서 첫 번째 문자는 문자 위치 147 같은 버퍼를 기반으로 합니다.  사용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> 버퍼에서를 1 차원 위치에 액세스할 수 있는 인터페이스입니다.  2 차원 좌표계는 줄 고 인덱스 쌍을 기반으로 합니다.  예를 들어, 문자 버퍼 43 5 43 줄 해당 줄에서 첫 번째 문자의 오른쪽 5 개 문자를 수 있습니다.  2 차원 위치를 사용 하 여 버퍼에 액세스를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 인터페이스입니다.  모두는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream> 인터페이스는 텍스트 버퍼 개체에 의해 구현 됩니다 \(<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>\)를 사용 하 여 액세스할 수 있습니다 `QueryInterface`.  다음은 이러한 기능 및 기타 주요 인터페이스 표시 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>.  
  
 ![텍스트 버퍼 개체](~/docs/extensibility/media/vstextbuffer.gif "vsTextBuffer")  
텍스트 버퍼 개체  
  
 텍스트 버퍼에서 두 좌표계를 작동 하지만 2 차원 좌표를 사용 하도록 최적화 되었습니다.  1 차원 좌표 시스템 성능 오버 헤드를 만들 수 있습니다.  따라서 가능 하면 2 차원 좌표 시스템을 사용 합니다.  
  
 텍스트 버퍼의 두 번째 책임은 보존 파일입니다.  이렇게 하려면 텍스트 버퍼 개체가 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> 는 문서 데이터 개체 구성 프로젝트 항목에 대 한 지 속성에 포함 된 다른 환경의 구성 요소 역할을 하 고 있습니다.  자세한 내용은 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)를 참조하십시오.  
  
## 단원 내용  
 [레거시 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)  
 레거시 API를 사용 하는 보기 설정을 변경 하는 방법에 설명 합니다.  
  
 [텍스트 관리자를 사용 하 여 전역 설정 모니터링](../extensibility/using-the-text-manager-to-monitor-global-settings.md)  
 텍스트 관리자를 사용 하 여 전역 설정을 모니터링 하는 방법에 설명 합니다.  
  
## 참고 항목  
 [코어 편집기 내](../extensibility/inside-the-core-editor.md)