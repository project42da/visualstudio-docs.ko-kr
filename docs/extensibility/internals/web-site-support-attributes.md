---
title: "웹 사이트의 지원 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "웹 사이트 프로젝트의 경우 등록"
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# 웹 사이트의 지원 속성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]웹 사이트 프로젝트 프로그래밍 언어 웹 지원 하에 확장할 수 있습니다.  언어 자체를 등록 해야 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 서식 파일에 나타날 수 있도록는  **새 웹 사이트** 는 언어를 선택 하면 대화 상자.  
  
 IronPython Studio 샘플 웹 사이트 지원을 제공합니다.  찾을 수 있습니다.의 [VSSDK 샘플](../../misc/vssdk-samples.md).  IronPython 코드 숨김 언어 새 웹 프로젝트에 대 한 등록은 다음과 같은 특성 클래스를 포함 합니다.  
  
## WebSiteProjectAttribute  
 이 특성에는 언어 프로젝트에 배치 됩니다.  웹 프로그래밍 언어의 목록에서 언어를 추가  **언어** 에  **새 웹 사이트** 대화 상자.  예를 들어, 다음 Ironpython을 목록에 추가합니다.  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 또한이 특성 서식 파일 폴더를 지정 하는 서식 파일 경로 설정 합니다.  Templates 폴더의 위치에 대 한 자세한 내용은 [템플릿을 지 원하는 웹 사이트](../../extensibility/internals/web-site-support-templates.md).  
  
## WebSiteProjectRelatedFilesAttribute  
 이 특성에는 언어 프로젝트에 배치 됩니다.  이 파일 유형 \(관련\)를 중첩 하는 웹 사이트 프로젝트를 다른 파일 형식 \(기본\)에서 있습니다 해당  **솔루션 탐색기**.  
  
 예를 들면 다음과 같습니다.  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 IronPython 코드 숨김 파일은.aspx 파일에 관련 된 것을 지정 합니다.  새.aspx 웹 페이지는 IronPython 웹 사이트 솔루션을 만들 때 새.py 소스 파일이 생성 되 고.aspx 페이지의 자식 노드로 나타납니다.  
  
## ProvideIntellisenseProviderAttribute  
 이 특성은 언어 프로젝트에서 패키지에 배치 됩니다.  Intellisense는 언어에 대 한 공급자를 선택합니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 지정 하는 인스턴스를 구현 하는 PythonIntellisenseProvider <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, 언어 서비스를 제공 하도록 요청 시 작성 해야 합니다.  
  
 IVsIntellisenseProject 구현을 참조를 처리 하 고 코드가 포함 된 웹 페이지를 요청 했지만 캐시 되지 않은 경우 언어 컴파일러를 호출 합니다.  
  
## 참고 항목  
 [웹 사이트 지원](../../extensibility/internals/web-site-support.md)