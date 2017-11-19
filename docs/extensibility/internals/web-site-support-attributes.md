---
title: "웹 사이트 지원 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 504046999814b4766fa9e5e8c006a02049e7007d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="web-site-support-attributes"></a>웹 사이트의 지원 속성
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]웹 사이트 프로젝트 프로그래밍 언어 웹에 대 한 지원을 제공 하기 위해 확장할 수 있습니다. 언어를 사용 하 여 등록 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 템플릿에 나타날 수 있도록는 **새 웹 사이트** 대화 상자는 언어를 선택 합니다.  
  
 IronPython Studio 샘플 웹 사이트 지원이 포함 됩니다. 새 웹 프로젝트에 대 한 코드 숨김 언어로 IronPython를 등록 하는 다음 특성 클래스가 포함 됩니다.  
  
## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute  
 이 특성은 언어 프로젝트에 배치 됩니다. 웹에서 프로그래밍 언어의 목록에 언어 추가 **언어** 목록에 **새 웹 사이트** 대화 상자. 예를 들어 다음 IronPython 목록에 추가 합니다.  
  
```  
[WebSiteProject("IronPython", "Iron Python")]public class PythonProjectPackage : ProjectPackage  
```  
  
 이 특성에는 또한 서식 파일 경로 템플릿 폴더를 가리키도록 설정 합니다. 템플릿 폴더의 위치에 대 한 자세한 내용은 참조 하십시오. [웹 사이트 템플릿을 지 원하는](../../extensibility/internals/web-site-support-templates.md)합니다.  
  
## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute  
 이 특성은 언어 프로젝트에 배치 됩니다. 허용 되는 파일 형식 (관련)을 중첩 하는 웹 사이트 프로젝트에서 다른 파일 형식 (기본)는 **솔루션 탐색기**합니다.  
  
 예:  
  
```  
[WebSiteProjectRelatedFiles("aspx", "py")]public class PythonProjectPackage : ProjectPackage  
```  
  
 IronPython 코드 숨김 파일.aspx 파일 관련이 있는지를 지정 합니다. IronPython 웹 사이트 솔루션에 새.aspx 웹 페이지가 만들어지면 새.py 소스 파일을 생성 되 고.aspx 페이지의 자식 노드로 나타납니다.  
  
## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute  
 이 특성은 언어 프로젝트 패키지에 배치 됩니다. 언어에 대 한 Intellisense 공급자를 선택합니다.  
  
 예:  
  
```  
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]public class PythonPackage : Package, IOleComponent  
```  
  
 지정 PythonIntellisenseProvider 구현 하는 인스턴스의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, 언어 서비스를 제공 하는 요청에 만들어야 합니다.  
  
 IVsIntellisenseProject 구현을 참조를 처리 하 고 웹 페이지 코드를 요청 했지만 캐시 되지 않고 때 언어 컴파일러를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [웹 사이트 지원](../../extensibility/internals/web-site-support.md)