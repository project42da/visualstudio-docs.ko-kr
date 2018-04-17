---
title: 웹 사이트 템플릿을 지 원하는 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- we site projects, templates
ms.assetid: 37173c97-486b-4b3c-8ed3-cf5890c4de23
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: af8e0d845157b475e4a5527443f55286828023cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="web-site-support-templates"></a>웹 사이트 지원 서식 파일
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 웹 사이트 프로젝트 및 항목 템플릿을 처음부터 새 웹 사이트 프로젝트와 항목을 만들 필요성을 제거 하 여 개발 프로세스를 가속화할 재사용 및 사용자 지정 가능한 웹 사이트 프로젝트와 항목 스텁을 제공 합니다. 대 한 자세한 내용은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 템플릿 참조 [프로젝트 만들기 및 항목 템플릿](../../ide/creating-project-and-item-templates.md)합니다.

## <a name="project-template-folder"></a>프로젝트 템플릿 폴더
 웹 프로젝트 템플릿은 일반적으로에 설치 [*Visual Studio 설치 경로*] \Common7\IDE\ProjectTemplates\Web\\, 웹 프로그래밍 언어를 따서 명명 된 하위 폴더에 각각 있습니다.

## <a name="project-file"></a>프로젝트 파일
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) 템플릿을 올바른 프로젝트 형식에 매핑하는 방법으로 프로젝트 파일 확장명이 있어야 합니다. 웹 프로젝트에 프로젝트 파일이 없기 때문에 서식 파일 프로젝트 형식에 매핑할 더미 프로젝트 파일 확장명.webproj 등록 됩니다.

 필요에 따라 언어 이름 문자열 수에 언어 기본 설정 하도록 웹 프로젝트 시스템에 사용할 수 있도록 템플릿에 추가할 수는 **새 항목 추가** 항목에 대 한 대화 상자 템플릿을 기반으로 합니다. 문자열에는 파일의 첫 번째 줄 이어야 합니다. IntelliSense 엔진 등록에 AddItemLanguageName 등록 이름과 프로젝트 Subtype(VsTemplate) 아래에서 등록 되는 이름 일치 해야 합니다. 자세한 내용은 참조 [웹 사이트 지원 특성](../../extensibility/internals/web-site-support-attributes.md)합니다.

 문자열이 없는 경우 웹 프로젝트 시스템은 프로젝트 템플릿을 통해 웹 프로젝트에 추가 하는 페이지의 언어 특성 및 파일 확장명에 따라 기본 언어를 결정 하려고 합니다.

## <a name="project-templates"></a>프로젝트 템플릿
 웹 사이트 프로젝트 템플릿 대 한 응답으로 새 웹 사이트를 만드는 데 사용 되는 **새 웹 사이트** 명령을 **파일** 메뉴. 웹 사이트 프로젝트 유형은 현재 지원 됩니다.

-   빈 웹 사이트 프로젝트

-   웹 사이트 프로젝트

-   웹 서비스 프로젝트

### <a name="empty-web-site-projects"></a>빈 웹 사이트 프로젝트
 이러한 파일에 대 한 응답에서 새 빈 웹 사이트를 만들는 **빈 웹 사이트** 선택한 후 사용할 수 있는 명령 **파일** > **새 웹 사이트**:

-   EmptyWeb.vstemplate

     새 빈 웹 사이트 작성 과정을 안내 하는 템플릿 파일입니다.

-   EmptyWeb.webproj

     이 파일은 프로젝트 템플릿 시스템의 아티팩트입니다. EmptyWeb.vstemplate 파일에서 프로젝트 파일 참조를 충족 합니다.

### <a name="web-site-projects"></a>웹 사이트 프로젝트
 이러한 파일에 대 한 응답에서 새 웹 사이트 만들기는 **ASP.NET 웹 사이트** 선택한 후 사용할 수 있는 명령 **파일** > **새 웹 사이트**:

-   Default.aspx

     새 웹 사이트에 대 한 기본 홈 페이지입니다. Language 특성 코드 숨김 언어를 지정 하 고 CodeFile 특성이이 페이지와 관련 된 코드 숨김 코드를 포함 하는 종속 파일을 지정 합니다.

-   Default.aspx.*extension*

     기본 홈 페이지에 대 한 코드 숨김 코드를 포함 하는 종속 파일 코드 숨김 언어에 따라 결정 된 *확장* 이 파일의 합니다.

-   web.config

     루트 web.site 구성 파일입니다.

-   WebApplication.vstemplate

     웹 사이트 솔루션의 내용을 결정 하 고 App_Data 폴더 만들기를 적용 하는 템플릿 파일입니다.

-   WebApplication.webproj

     이 파일은 프로젝트 템플릿 시스템의 아티팩트입니다. WebApplication.vstemplate 파일에서 프로젝트 파일 참조를 충족 합니다.

### <a name="web-service-projects"></a>웹 서비스 프로젝트
 이러한 파일에 대 한 응답에서 새 웹 사이트 만들기는 **ASP.NET 웹 서비스** 선택한 후 사용할 수 있는 명령 **파일** > **새 웹 사이트**:

-   Service.asmx

     새 웹 서비스에 대 한 HTML 페이지입니다. 코드 숨김 언어를 지정 하는 언어 특성 및 코드 숨김 특성은이 서비스와 연결 된 코드 숨김 코드를 포함 하는 종속 파일을 지정 합니다.

-   서비스입니다. *extension*

     서비스 클래스를 구현 하는 종속 파일 코드 숨김 언어에 따라 결정 된 *확장* 이 파일의 합니다.

-   web.config

-   루트 web.site 구성 파일입니다.

-   WebService.vstemplate

     웹 사이트 솔루션의 내용을 결정 하 고 강제로 App_Code 및 App_Data 폴더가 생성 하는 템플릿 파일입니다. 서비스입니다. *확장* 파일이 App_Code 폴더에 복사 됩니다.

-   WebService.webproj

     이 파일은 프로젝트 템플릿 시스템의 아티팩트입니다. WebService.vstemplate 파일에서 프로젝트 파일 참조를 충족 합니다.

## <a name="project-item-template-folder"></a>프로젝트 항목 템플릿 폴더
 웹 프로젝트 항목 템플릿을 일반적으로에 설치 [*Visual Studio 설치 경로*] \Common7\IDE\ItemTemplates\Web\\, 각각의 웹 프로그래밍 언어를 따서 명명 된 하위 폴더에 있습니다.

## <a name="project-item-templates"></a>프로젝트 항목 템플릿
 웹 사이트 프로젝트 항목 템플릿은 새 웹 페이지에 대 한 응답에서 웹 사이트를 추가 하는 데 사용 되는 **기존 항목 추가** 명령입니다. 이러한 종류의 웹 페이지는 현재 지원 됩니다.

-   새 클래스

-   새 HTML 페이지

-   새 Web Form

-   새 마스터 페이지

### <a name="new-class"></a>새 클래스
 이 서식 파일에 대 한 응답에는 빈 클래스를 정의 하는 새 소스 파일을 만듭니다는 **새 클래스 추가** 명령입니다.

-   클래스입니다. *extension*

     빈 클래스를 구현 하는 원본 파일입니다. 코드 숨김 언어에 따라 결정 된 *확장* 이 파일의 합니다.

-   Class.vstemplate

     소스 파일을 만들고 해당 콘텐츠를 결정 하는 템플릿 파일입니다.

### <a name="new-html-page"></a>새 HTML 페이지
 이 서식 파일에 대 한 응답에서 웹 페이지를 새로 만들어는 **새 HTML 페이지 추가** 명령입니다.

-   HTMLPage.htm

     웹 페이지의 시작 하는 내용입니다. 일반적으로이 웹 페이지에 없는 관련된 코드 숨김 종속 파일이 있습니다. 스마트 페이지 관련된 코드 숨김 파일을 만들려면 웹 양식 서식 파일을 대신 사용 합니다.

-   HTMLPage.vstemplate

     웹 페이지를 만들고 해당 콘텐츠를 결정 하는 템플릿 파일입니다.

### <a name="new-webform"></a>새 WebForm
 이 서식 파일에 대 한 응답에서 스마트 웹 페이지를 새로 만들어는 **새 Web Form 추가** 명령입니다.

 코드 숨김 종속 소스 파일을 만들려면 선택 **별도 파일에 코드 입력**합니다. 그렇지 않으면 단일 웹 페이지 만들어지면 빈 스크립트 블록 및 0 \<페이지 % % > 지시문 종속 파일을 연결 합니다.

 선택 된 마스터 페이지에 대 한 콘텐츠 페이지를 만들려면 선택 **마스터 페이지 선택**합니다.

-   WebForm.aspx

     웹 페이지의 시작 하는 내용입니다. 이 웹 페이지에 연결 된 코드 숨김 종속 파일이 없습니다.

-   WebForm_cb.aspx

     웹 페이지의 시작 하는 내용입니다. 이 웹 페이지에는 관련된 코드 숨김 종속 파일이 있습니다.

-   코드 숨김 합니다. *extension*

     Webform 클래스를 구현 하는 종속 파일 코드 숨김 언어에 따라 결정 된 *확장* 이 파일의 합니다.

-   ContentPage.aspx

     콘텐츠 페이지와 웹 페이지의 시작 하는 내용입니다. 이 웹 페이지에 연결 된 코드 숨김 종속 파일이 없습니다.

-   ContentPage_cb.aspx

     콘텐츠 페이지와 웹 페이지의 시작 하는 내용입니다. 이 웹 페이지에는 관련된 코드 숨김 종속 파일이 있습니다.

-   WebForm.vstemplate

     새 웹 페이지 및 해당 종속 파일의 내용을 결정 하는 템플릿 파일입니다.

### <a name="new-master-page"></a>새 마스터 페이지
 이 서식 파일에 대 한 응답에서 마스터 페이지를 새로 만듭니다는 **새 마스터 페이지 추가** 명령입니다.

 코드 숨김 종속 소스 파일을 만들려면 선택 **별도 파일에 코드 입력**합니다. 그렇지 않으면 단일 웹 페이지 만들어지면 빈 스크립트 블록 및 아니요 \<페이지 % % > 지시문 종속 파일을 연결 합니다.

-   MasterPage.master

     마스터 페이지의 시작 하는 내용입니다. 이 마스터 페이지에 연결 된 코드 숨김 종속 파일이 없습니다.

-   MasterPage_cb.master

     마스터 페이지의 시작 하는 내용입니다. 이 마스터 페이지에는 관련된 코드 숨김 종속 파일이 있습니다.

-   코드 숨김 합니다. *확장*

     마스터 페이지 클래스를 구현 하는 종속 파일 코드 숨김 언어에 따라 결정 된 *확장* 이 파일의 합니다.

-   MasterPage.vstemplate

     새 마스터 페이지 및 해당 종속 파일의 내용을 결정 하는 템플릿 파일입니다.

## <a name="see-also"></a>참고 항목
 [웹 사이트 지원](../../extensibility/internals/web-site-support.md)