---
title: "웹 사이트 지원 특성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- web site projects, registration
ms.assetid: 46d52e2c-ca2a-4bbd-8500-5b0129768aec
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 66e9dcfd511a95ce1ea27af64a3a7f8302fe2827
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="web-site-support-attributes"></a>웹 사이트의 지원 속성
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 웹 사이트 프로젝트 프로그래밍 언어 웹에 대 한 지원을 제공 하기 위해 확장할 수 있습니다. 언어를 사용 하 여 등록 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 템플릿에 나타날 수 있도록는 **새 웹 사이트** 대화 상자는 언어를 선택 합니다.

IronPython Studio 샘플 웹 사이트 지원이 포함 됩니다. 샘플은 IronPython 새 웹 프로젝트에 대 한 코드 숨김 언어도 등록 하는 다음 특성 클래스를 포함 합니다.

## <a name="websiteprojectattribute"></a>WebSiteProjectAttribute
 이 특성은 언어 프로젝트에 배치 됩니다. 웹에서 프로그래밍 언어의 목록에 언어 추가 **언어** 목록에 **새 웹 사이트** 대화 상자. 예를 들어 다음 코드는 IronPython 목록에 추가 합니다.

```
[WebSiteProject("IronPython", "Iron Python")]
public class PythonProjectPackage : ProjectPackage
```

 이 특성에는 또한 서식 파일 경로 템플릿 폴더를 가리키도록 설정 합니다. 템플릿 폴더의 위치에 대 한 자세한 내용은 참조 하십시오. [웹 사이트 템플릿을 지 원하는](../../extensibility/internals/web-site-support-templates.md)합니다.

## <a name="websiteprojectrelatedfilesattribute"></a>WebSiteProjectRelatedFilesAttribute
 이 특성은 언어 프로젝트에 배치 됩니다. 허용 되는 파일 형식 (관련)을 중첩 하는 웹 사이트 프로젝트에서 다른 파일 형식 (기본)는 **솔루션 탐색기**합니다.

 예를 들어 다음 코드는.aspx 파일에 IronPython 코드 숨김 파일이 관련 되었음을 지정 합니다. IronPython 웹 사이트 솔루션에 새.aspx 웹 페이지가 만들어지면 새.py 소스 파일을 생성 되 고.aspx 페이지의 자식 노드로 나타납니다.

```
[WebSiteProjectRelatedFiles("aspx", "py")]
public class PythonProjectPackage : ProjectPackage
```

## <a name="provideintellisenseproviderattribute"></a>ProvideIntellisenseProviderAttribute
 이 특성은 언어 프로젝트 패키지에 배치 됩니다. 언어에 대 한 IntelliSense 공급자를 선택합니다.

 예를 들어 다음 코드에서는 지정 하는 PythonIntellisenseProvider 구현 하는 인스턴스의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject>, 언어 서비스를 제공 하는 요청에 만들어야 합니다.

```
[ProvideIntellisenseProvider(typeof(PythonIntellisenseProvider), "IronPythonCodeProvider", "Iron Python", ".py", "IronPython;Python", "IronPython")]
public class PythonPackage : Package, IOleComponent
```

 IVsIntellisenseProject 구현을 참조를 처리 하 고 있는 웹 페이지 코드를 요청 했지만 캐시 되지 않을 경우 언어 컴파일러를 호출 합니다.

## <a name="see-also"></a>참고 항목
 [웹 사이트 지원](../../extensibility/internals/web-site-support.md)